pipeline {
    agent any
    environment {
            AWS_ACCESS_KEY_ID = credentials("aws_access_key_id")
            AWS_SECRET_ACCESS_KEY = credentials("aws_secret_access_key")
            AWS_DEFAULT_REGION = credentials("aws_default_region")
        }
    stages {
        stage('Build') {
            steps {
                git branch:"main", url:'https://github.com/AhmedNabilSharawy/CICD_Eks_app.git'
            }
        }
        stage('Ci-CD') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'docker', usernameVariable: 'myuser', passwordVariable: 'mypass')]) {
                sh """
                 docker build --network=host . -t ahmednabilsharawy/hello_nabil:1
                 docker login -u ${myuser} -p ${mypass}
                 docker push ahmednabilsharawy/hello_nabil:1 
                """
            }
        }
        }
        stage('Deploy to Kubernetes') {
            steps {
                sh '''
                    aws eks update-kubeconfig --name Nabil-Eks-Cluster --region us-east-1
                    export KUBECONFIG=~/.kube/config
                    kubectl apply -f app.yaml
                '''
            }
            }

}
}



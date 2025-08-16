pipeline {
    agent any
    environment {
        // ✅ Replace X with your actual AWS ECR repo if different
        ECR_REPO = "X"  

        // ✅ Replace X if your kubeconfig path is different
        KUBECONFIG = "X"   // Ensure Jenkins uses the correct kubeconfig
    }
    stages {
        stage('Checkout') {
            steps {
                // ✅ Replace X with your repo URL and branch if different
                git branch: 'main', url: 'X'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $ECR_REPO:latest .'   // Uses ECR_REPO defined above
            }
        }
        stage('Push to ECR') {
            steps {
                sh 'aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin $ECR_REPO'
                sh 'docker push $ECR_REPO:latest'
            }
        }
        stage('Deploy to Kubernetes') {
            steps {
                // Debug: Verify that the k8s directory and deployment.yaml file exists
                sh 'ls -l k8s/'

                // Debug: Show the contents of the deployment.yaml file
                sh 'cat k8s/deployment.yaml'

                // ✅ Replace X with your actual EKS cluster name
                sh '''
                    echo "Verifying Kubernetes connection"
                    X # Replace X with your EKS cluster name
                    kubectl cluster-info || { echo "Kubernetes connection failed"; exit 1; }
                '''

                // ✅ Replace X with the correct deployment file if different
                sh '''
                    echo "Applying Kubernetes deployment"
                    X || { echo "Kubernetes deployment failed"; exit 1; }
                '''
            }
        }
    }
}

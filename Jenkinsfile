pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                echo 'Cloning repository...'
            }
        }

        stage('Build Docker Image') {
            steps {
                echo 'Building Docker image...'
                sh 'docker build -t my-app .'
            }
        }

        stage('Deploy to Kubernetes') {
    steps {
        sh '''
        kubectl apply -f k8s/deployment.yaml
        kubectl apply -f k8s/service.yaml
        '''
    }
}

    }
}

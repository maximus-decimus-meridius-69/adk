pipeline {
    agent any 

    stages {
        stage('Build') {
            steps {
                script {
                    bat 'docker login -u yaswanthkumar07 -p Yash@4606'
                    bat 'docker build -t w9-dd-app:latest .'
                    bat 'docker tag w9-dd-app:latest yaswanthkumar07/w9-dh-app:latest'
                    bat 'docker push yaswanthkumar07/w9-dh-app:latest'
                }
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
            }
        }

        stage('Deploy') {
            steps {
                script {
                    bat 'kubectl apply -f my-kube1-deployment.yaml'
                    bat 'kubectl apply -f my-kube1-service.yaml'
                    echo 'Deploying application to Docker Desktop Kubernetes...'
                }
            }
        }
    }
}

pipeline {
    agent any

    stages {
    /*    stage('Security Tests') {
            steps {
                // Your security tests commands here
                sh 'python -m pytest tests' // Example using pytest
            }
        } */
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build("taeahmed/simple_flask_app:latest")
                }
            }
         }   
    /*    stage('Security Scan') {
            steps {
                sh 'trivy image taeahmed/simple_flask_app:latest'
            }
        } */
        stage('Push Docker Image') {
            steps {     
                script {
                    docker.withRegistry('https://index.docker.io/v1/', credentialsId: 'docker-hub-creds') {
                        docker.image("taeahmed/simple_flask_app:latest").push() 
                    }
                }           
            }
        }
    }
}


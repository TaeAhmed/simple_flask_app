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
            ageant {
                docker { 
                    docker.build("taeahmed/simple_flask_app:latest")
                }
            }
            steps {
            
            }
         }   
    /*    stage('Security Scan') {
            steps {
                sh 'trivy image taeahmed/simple_flask_app:latest'
            }
        } */
        stage('Push Docker Image') {
            ageant {
                docker {
                    docker.push("taeahmed/simple_flask_app:latest")
                }
            }
            steps {     
                
            }
        }
    }
}


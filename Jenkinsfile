pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                echo 'Hello Abhilash'
                sh '''
                ls -la
                node --version
                npm --version
                npm ci
                npm run build
                ls -la
                '''
                
            }
        }
        stage ('Test') {
            steps {
                echo 'Running Tests'
            }
        }

        }
    }



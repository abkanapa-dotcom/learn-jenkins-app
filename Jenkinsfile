pipeline {
    agent any

    stages {
        //This si Build Stage
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            /*
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
                
            }*/
        }
        //This is Test Stage
        stage ('Test') {
            steps {
                echo 'Testing Application'     
            }
                
            
        }

    }
    post {
        always {
            junit 'test-results/junit.xml'
        }
    }
}


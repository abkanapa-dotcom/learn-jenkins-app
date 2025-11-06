pipeline {
    agent any

    stages {
        //This si Build Stage
        /*
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
                
            }*/
        }
        //This is Test Stage
        stage ('Test') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                echo 'Testing Application'
                sh 'test -f build/index.html'
                npm test

            }
                
            
        }

    
    post {
        always {
            junit 'test-results/junit.xml'
           sh '''
           # npm test
           '''
        }
    }
}


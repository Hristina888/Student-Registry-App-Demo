pipeline{

    agent any

    environment{
        NODE_VERSION = '18.x'
    }

    tools{
        nodejs "${NODE_VERSION}"
    }

    stages {
        stage ('Checkout'){
            steps{
                git branch: 'main', url: 'https://github.com/Hristina888/Student-Registry-App-Demo'
            }
        }

        stage ('Install dependensies'){
            steps{
                script{
                       bat 'npm install'
                }
            }
        }

        stage ('Start app and run tests'){
            steps{
                script{
                    bat 'npm start &'
                    bat 'wait-on http://localhost:8090'
                    bat 'npm test'
                }
            }
        }
    }

    post {
        always{
            echo "CI pipeline completed"
        }
    }
        
}
pipeline{

    agent any

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
                    bat 'start /b npm start'
                    
                }
            }
        }
        stage('run tests')
        {
            steps{
                script{
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
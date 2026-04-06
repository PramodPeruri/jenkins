pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying'
            }
        }
        
    }
    post {
         always {
            cleanWs() // Deletes the entire workspace
          }
         success {
                echo 'I will run if success'
         }
         failure{
               echo 'I will run if failure'
         }

        }
}
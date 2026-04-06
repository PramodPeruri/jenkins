pipeline {
    agent {
        node{
            label 'AGENT-1'
        }
    }
    environment {
        COURSE= "Jenkins"
    }
    options {
        timeout(time: 10, unit: 'SECONDS')
    }
    stages {
        stage('Build') {
            steps {
                script{
                   sh """
                       echo "Building"
                       echo $COURSE
                       sleep 10
                   """
                }
                
            }
        }
        stage('Test') {
            steps {
                script{
                   sh """
                       echo "Testing"
                   """
                }
            }
        }
        stage('Deploy') {
            steps {
                script{
                   sh """
                       echo "Deploying"
                   """
                }
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
         aborted {
            echo 'pipelines is aborted'
         }

        }
}
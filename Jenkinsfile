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
            input {
                message "Should we continue?"
                ok "Yes, we should."
                submitter "alice,bob"
                parameters {
                    string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
                }
            }
            steps {
                script{
                   sh """
                       echo "Deploying."
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

        }
}
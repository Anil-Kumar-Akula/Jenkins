pipeline {
    agent {
       node {
          label 'AGENT-1'
       }
    }
    stages {
       stage('Build')  {
         steps {
           echo "Building"
         }
       }
        stage('Test') { 
          steps {
            echo "Testing"
          }
        }
        stage('Deploy') {
           steps {
             echo "Deploying"
           }
        }
 
    }
    post {
        always {
            echo "I always say Hello..!"
            cleanWs()
        }
        success {
             echo "i will run if successfull"
        }
        failure {
             echo "i will run if failure"
        }
    }
     
}
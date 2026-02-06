pipeline {
    agent {
       node {
          label 'AGENT-1'
       }
    }
    stages {
       stage('Build')  {
         steps {
           script {
             sh """
               echo "By using the Hybrid method building the pipeline"

               """
           }
         }
       }
        stage('Test') { 
          steps {
            script {
              sh """
                 echo "By using the Hybrid method testing the pipeline"

                 """
            }
           
          }
        }
        stage('Deploy') {
           steps {
             script {
                sh """
                echo "By using the Hybrid method deploying the pipeline"

                """
             }
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
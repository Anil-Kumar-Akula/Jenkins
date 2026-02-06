pipeline {
    agent {
       node {
          label 'AGENT-1'
       }
    }
    environment {
         COURSE = "jenkins"
    }
    stages {
       stage('Build')  {
         steps {
           script {
             sh """
               echo "By using the Hybrid method building the pipeline"
               echo $COURSE
               """
           }
         }
       }
        stage('Test') { 
          steps {
            script {
              sh """
                 echo "By using the Hybrid method testing the pipeline"
                 echo $COURSE
                 env
                 """
            }
           
          }
        }
        stage('Deploy') {
           steps {
             script {
                sh """
                echo "By using the Hybrid method deploying the pipeline"
                echo $COURSE
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
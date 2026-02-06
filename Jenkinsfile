pipeline {
    agent {
       node {
          label 'AGENT-1'
       }
    }
    environment {
         COURSE = "jenkins"
    }
    options {
        timeout(time: 10, unit: 'MINUTES') 
        disableConcurrentBuilds()
    }
     parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    stages {
       stage('Build')  {
         steps {
           script {
             sh """
                echo "By using the Hybrid method building the pipeline"
                echo $COURSE
                env

                echo "Hello ${params.PERSON}"

                echo "Biography: ${params.BIOGRAPHY}"

                echo "Toggle: ${params.TOGGLE}"

                echo "Choice: ${params.CHOICE}"

                echo "Password: ${params.PASSWORD}"
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
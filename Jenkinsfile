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

        booleanParam(name: 'DEPLOY', defaultValue: false, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    // This is building stage
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

                echo "Toggle: ${params.DEPLOY}"

                echo "Choice: ${params.CHOICE}"

                echo "Password: ${params.PASSWORD}"
               """
           }
         }
       }
       // This is Testing stage
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
        //    input {
        //         message "Should we continue?"
        //         ok "Yes, we should."
        //         submitter "alice,bob"
        //         parameters {
        //             string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        //         }
        //     }
        when {
            expression { "$params.DEPLOY" }
            }

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
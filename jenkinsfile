pipeline {
    agent any
    environment {
        name = 'Mangesh'
    }
    parameters{
        string(name: 'Person', defaultValue: 'Saurav Sharma', description: "who are you?")
        booleanParam(name: 'isMale ', defaultValue: true, description: "")
        choice(name: 'City', choices: ['jaipur','mumbai','pune'], description: "")
    }
    stages {
        stage('test') {
            steps {
                sh '''
                ls
                pwd
                date
                ip a
                '''
            }
        }
         stage('enviroment variables') {
             environment {
                 username = 'jetking'
             }
            steps {
                sh  'echo "${BUILD_ID}"'
                 sh  'echo "${name}"'
                 sh  'echo "${username}"'
            }
        }
         stage('test-prod') {
            steps {
                echo 'test-prod'
                sh  'echo "${name}"'
                sh  'echo "${Person}"'
            }
        }
         stage('prod-deploy') {
             input {
                 message "should we continue?"
                 ok "yes we should"
             }
            steps {
                echo 'prod-deploy'
            }
        }
    }
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
        failure {
            echo 'failure'
        }
        success {
            echo 'success'
        }
    }
}

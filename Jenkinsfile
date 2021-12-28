pipeline {
    agent any
    
    stages {
        stage('Example') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Build') {
          steps {
            checkout scm
            sh "npm install"
            stash includes: 'node_modules/', name: 'node_modules'
          }
        }

        stage('Test') {
          steps {
            unstash 'node_modules'
            sh "npm run test"
          }
        }
    }
    post { 
        always { 
            echo 'I will always say Hello again!!!'
        }
    }
}

// This file is checked into source control(root directory of repo by default)
// Declarative Pipeline
pipeline {
    agent any
    
    stages {
        stage('Pre-build (Manually)') {
            input {
                message "Continue to next step?"
                ok "Yes"
                submitter "submitter"
                parameters {
                    string(name: 'Signature', defaultValue: 'Mr Jenkins', description: 'Signature')
                }
            }
            steps {
                echo "The following steps have been permitted by ${Signature}"
            }
        }

        stage('Build: Run Simple.bat') {
            steps {
                echo 'Building..'
                echo 'This sample is from the following webpage'
                //https://jenkins.io/zh/doc/book/pipeline/jenkinsfile/
            }
        }
        
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
    
    
    post { 
        always { 
            echo 'This will be executed always!'
        }
        success{
            echo 'This will be executed when success'
        }
        aborted {
            echo 'This will be executed when aborted'
        }
        failure {
            echo 'This will be executed when failure'
        }
        changed {
            echo 'This will be executed when changed'
        }
        unstable{
            echo 'This will be executed when unstable'
        }
    }
}

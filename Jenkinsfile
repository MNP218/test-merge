pipeline {
    agent any

    stages {
        stage('Checkout codes'){
            steps {
                checkout scm
                sh "git status"
            }
        }
        
        stage('Info') {
            steps {
                script {
                    branch_name = sh (
                        script: """git status | grep "On branch" | sed 's/On branch//g'""",
                        returnStdout: true
                        ).trim()
                    currentBuild.description = "Build ${branch_name} branch"
                }
            }
        }

        stage('Build') {
            steps {
                echo 'Compiling codes ...'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests ...'
            }
        }

        stage('Push') {
            steps {
                echo 'Pushing to Docker registry ...'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deployment in progress ...'
            }
        }
    }
}

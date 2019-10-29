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
                    currentBuild.description = "Build $GIT_BRANCH branch"
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

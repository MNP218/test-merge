pipeline {
    agent any

    stages {
        stage('Info') {
            steps {
                script {
                    currentBuild.description = "Build $BRANCH branch"
                }
            }
        }
        
        stage('Checkout codes'){
            steps {
                checkout scm
                sh "git status"
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

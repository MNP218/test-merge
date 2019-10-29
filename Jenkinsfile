pipeline {
    agent any

    parameters {
        gitParameter branchFilter: 'origin/(.*)', defaultValue: 'develop', name: 'BRANCH', type: 'PT_BRANCH'
    }

    stages {
        stage('Info') {
            steps {
                script {
                    currentBuild.description = "Build ${params.BRANCH} branch"
                }
            }
        }
        
        stage('Checkout codes'){
            steps {
                git branch: "${params.BRANCH}", credentialsId: '2b641c02-130f-4268-855e-c6141c1b954d', url: scm.getUserRemoteConfigs()[0].getUrl()
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

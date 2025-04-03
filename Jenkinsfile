pipeline {
    agent any

    stages {
        stage('install-pip-deps') {
            steps {
                bat "ls -a"
            }
        }
        stage('deploy-to-dev') {
            steps {
                echo 'Hello World2'
            }
        }
        stage('tests-on-dev') {
            steps {
                echo 'Hello World3'
            }
        }
        stage('deploy-to-staging') {
            steps {
                echo 'Hello World4'
            }
        }
        stage('tests-on-staging') {
            steps {
                echo 'Hello World5'
            }
        }
        stage('deploy-to-preprod') {
            steps {
                echo 'Hello World6'
            }
        }
        stage('tests-on-preprod') {
            steps {
                echo 'Hello World7'
            }
        }
        stage('deploy-to-prod') {
            steps {
                echo 'Hello World8'
            }
        }
        stage('tests-on-prod') {
            steps {
                echo 'Hello World9'
            }
        }
    }
}

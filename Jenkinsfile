pipeline {
    agent any

    stages {
        stage('install-pip-deps') {
            steps {
               echo 'Installing all required depdendencies'
            }
        }
        stage('deploy-to-dev') {
            steps {
                script {
                    deploy("dev")
                }
            }
        }
        stage('tests-on-dev') {
            steps {
                script {
                    tests("dev")
                }
            }
        }
        stage('deploy-to-staging') {
            steps {
                script {
                    deploy("staging")
                }
            }
        }
        stage('tests-on-staging') {
            steps {
                script {
                    tests("staging")
                }
            }
        }
        stage('deploy-to-preprod') {
            steps {
                script {
                    deploy("preprod")
                }
            }
        }
        stage('tests-on-preprod') {
            steps {
                script {
                    tests("preprod")
                }
            }
        }
        stage('deploy-to-prod') {
            steps {
                script {
                    deploy("prod")
                }
            }
        }
        stage('tests-on-prod') {
            steps {
                script {
                    tests("prod")
                }
            }
        }
    }
}

def deploy(String environment){
    echo "Deployment to ${environment} has started"
}
def tests(String environment){
    echo "Tests on ${environment} has started"
}

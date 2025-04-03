pipeline {
    agent any
    triggers { pollSCM '*/1 * * * *' }
    stages {
        stage('install-pip-deps') {
            steps {
               script {
                    build()
                }
            }
        }
        stage('deploy-to-dev') {
            steps {
                script {
                    deploy("dev", 7001)
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
                    deploy("staging", 7002)
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
                    deploy("preprod", 7003)
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
                    deploy("prod", 7004)
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
def build(){
    echo "Installing all required depdendencies"
    git branch: 'main', poll: false, url: 'https://github.com/mtararujs/python-greetings.git'
    bat "pip install -r requirements.txt"
}
def deploy(String environment, int port){
    echo "Deployment to ${environment} has started"
    git branch: 'main', poll: false, url: 'https://github.com/mtararujs/python-greetings.git'
    bat "pm2 delete greetings-app-${environment} & EXIT /B 0"
    bat "pm2 start app.py --name greetings-app-${environment} --port ${port}"
}
def tests(String environment){
    echo "Tests on ${environment} has started"
}

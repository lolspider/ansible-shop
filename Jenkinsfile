pipeline {
    agent {label 'stage-01'}
    environment {
        CHECK_URL = "http://localhost"
        CMD = "curl --write-out %{http_code} --silent --output /dev/null ${CHECK_URL}"
    }
    stages {
        stage("Fix the permission issue") {
            steps {
                sh "sudo chown root:vagrant /run/docker.sock"
            }
        }
        stage("pull image") {
            steps {
                sh 'docker pull springio/gs-spring-boot-docker'
                sh 'docker run -d -p 80:8080 springio/gs-spring-boot-docker'

            }
        }
        stage('Check-Stage-One') {
            steps {
                script{
                    sh "sleep 10"
                    sh "$CMD > commandResult"
                    env.status = readFile('commandResult').trim()
                }
            }
        }
        stage('Check-Stage-Two') {
            steps {
                script {
                    sh "echo ${env.status}"
                    if (env.status == '200') {
                        currentBuild.result = "SUCCESS"
                    }
                    else {
                        currentBuild.result = "FAILURE"
                    }
                }
            }
        }
    }
}

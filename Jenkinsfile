pipeline {
    agent any
    environment {
        PATH = "/home/ubuntu/apache-maven-3/bin:$PATH"
    }
    stages {
        stage('scm checkout') {
            steps {
                git 'https://github.com/jyo111/DevOps-Project.git'
            }
        }
        stage('build') {
            steps {
                sh 'mvn clean package'
            }
        }
    }
    post {
        success {
            slackSend baseUrl: 'https://hooks.slack.com/services/',
            channel: 'slack_practice',
            color: 'good',
            message: '"Build Started: ${env.JOB_NAME} ${env.BUILD_NUMBER}"',
            tokenCredentialId: 'slack_practice',
            username: 'jyothi'
        }
        failure {
            slackSend baseUrl: 'https://hooks.slack.com/services/',
            channel: 'slack_practice',
            color: 'red',
            message: '"Build Started: ${env.JOB_NAME} ${env.BUILD_NUMBER}"',
            tokenCredentialId: 'slack_practice',
            username: 'jyothi'
        }
    }
}

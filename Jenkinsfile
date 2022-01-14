pipeline {
    agent any
    environment {
        PATH = "/home/jyothi/apache-maven-3/bin:$PATH"
    }
    stages {
        stage('checkout the code from scm') {
            steps {
                git credentialsId: 'jenkins_github_pem', url: 'https://github.com/jyo111/DevOps-Project.git'
            }
        }
        stage('build') {
            steps {
                sh 'mvn clean install'
            }
        }        
    }
}

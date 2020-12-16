pipeline {
    agent any 
    environment {
        PATH ="/opt/apache-maven-3/bin:$PATH"
    }   
    stages {
        stage('SCM checkout') {
            steps {
                git 'https://github.com/jyo111/DevOps-Project.git'
            }
        }
        stage('compile-package') {
            steps {
                sh "mvn clean package"
            }
        }
        stage('email-notification') {
            steps {
                mail bcc: '',
                body: 'This is my first email pipeline',
                cc: 'jyothischalla@gmail.com',
                from: '',
                replyTo: '',
                subject: 'jenkins pipeline email',
                to: 'jyothichalla456@gmail.com'
            }
        }
    }
}

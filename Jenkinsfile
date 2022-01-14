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
        stage('deploy warfile to tomcat') {
            steps {
                sshagent(['jenkins_github_pem']) {               
                sh "scp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/tomcat_project/target/DevOpsRocks.war jyothi@3.144.245.42:/home/jyothi/tomcat-9/webapps"
                }
            }
        }
    }
}

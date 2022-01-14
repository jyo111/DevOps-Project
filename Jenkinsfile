pipeline {
    agent any
    environment {
        PATH = "/home/jyothi/apache-maven-3/bin:$PATH"
    }
    stages {
        stage('checkout the code from scm') {
            steps {
                git credentialsId: 'Jenkins_GitHub_Pem_key', url: 'https://github.com/jyo111/DevOps-Project.git'
            }
        }
        stage('build') {
            steps {
                sh 'mvn clean install'
            }
        }
        stage('deploy warfile to tomcat') {
            steps {
                sshagent(['Jenkins_GitHub_Pem_key']) {
                sh "scp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/tomcat_project/target/DevOpsRocks.war jyothi@172.31.27.20:/home/jyothi/tomcat-10/webapps"
                }
            }
        }
    }
}

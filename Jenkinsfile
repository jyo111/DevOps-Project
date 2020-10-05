pipeline {
    agent any
    environment {
        PATH = "/home/ubuntu/maven3/bin:$PATH"
    }
    stages {
        stage("Maven build") {
            steps {
                sh "mvn clean package"
            }
        }
    }
}

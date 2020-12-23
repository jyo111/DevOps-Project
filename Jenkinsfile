pipeline {
    agent any
    stages {
        stage('scm checkout') {
            steps {
                git 'https://github.com/jyo111/DevOps-Project.git'
            }
        }
        stage('ansible playbook execution') {
            steps {
                ansiblePlaybook credentialsId: 'ansible-jenkins',
                disableHostKeyChecking: true,
                installation: 'ansible',
                inventory: 'hosts',
                playbook: 'folder.yml'
            }
        }
    }
}

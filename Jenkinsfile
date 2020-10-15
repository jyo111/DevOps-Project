pipeline {
    agent any
    stages {
        stage('code clone') {
            steps {
                git 'https://github.com/jyo111/DevOps-Project.git'
            }
        }
        stage('execute ansible') {
            steps {
                ansiblePlaybook credentialsId: 'ubuntu-ansible-pipeline', disableHostKeyChecking: true, installation: 'ansible2', inventory: 'hosts', playbook: 'tree.yml'
            }
        }
    }
}

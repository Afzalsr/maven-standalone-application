pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Afzalsr/maven-standalone-application.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Deploy with Ansible') {
            steps {
                sh 'ansible-playbook ~/ansible-deploy/deploy.yml -i ~/ansible-deploy/inventory.ini'
            }
        }
    }
}


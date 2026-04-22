pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Divyyaasy/program4.git'
            }
        }

        stage('Build') {
            steps {
                dir('ansible-java-maven') {
                    bat 'mvn clean install'
                }
            }
        }

        stage('Deploy') {
            steps {
                dir('ansible-java-maven') {
                    bat 'wsl ansible-playbook -i inventory.ini deploy.yml'
                }
            }
        }
    }
}

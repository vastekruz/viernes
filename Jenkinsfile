pipeline {
    agent { label 'agent2' }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/vastekruz/viernes.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }

    post {
        always {
            junit 'target/surefire-reports/*.xml'
        }
    }
}
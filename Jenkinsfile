pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/SrikanthMortha/java-maven-devops-pipeline.git'
            }
        }

        stage('Build') {
            steps {
                script {
                    docker.image('maven:3.8.7-openjdk-17').inside {
                        sh 'mvn clean package'
                    }
                }
            }
        }

        stage('Test') {
            steps {
                junit '**/target/surefire-reports/*.xml'
            }
        }
    }
}


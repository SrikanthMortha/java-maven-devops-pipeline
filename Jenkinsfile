pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/SrikanthMortha/java-maven-devops-pipeline.git'
            }
        }

        stage('Build') {
            agent {
                docker {
                    image 'maven:3.8.7-openjdk-17'
                }
            }
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                junit '**/target/surefire-reports/*.xml'
            }
        }
    }
}


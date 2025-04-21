pipeline {
    agent any

    tools {
        maven 'Maven_3.8.7'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/SrikanthMortha/java-maven-devops-pipeline.git'
            }
        }

        stage('Build') {
            steps {
                dir('devopsapp') {
                    sh 'mvn clean package'
                }
            }
        }

        stage('Test') {
            steps {
                dir('devopsapp') {
                    junit '**/target/surefire-reports/*.xml'
                }
            }
        }
    }
}


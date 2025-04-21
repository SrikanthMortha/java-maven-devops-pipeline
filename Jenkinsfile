pipeline {
    agent any

    tools {
        maven 'Maven 3.8.7' // ✅ Exact name from Jenkins tool config
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


pipeline {
    agent any

    tools {
        maven 'Maven 3.8.7' // Make sure this is configured under Global Tool Configuration
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/SrikanthMortha/java-maven-devops-pipeline.git'
            }
        }

        stage('Build') {
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


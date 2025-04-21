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
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t devopsapp:v1 .'
            }
        }

        stage('Push to DockerHub/Registry') {
            steps {
                echo 'Pushing to DockerHub/Registry... (Coming soon)'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deployment step placeholder'
            }
        }
    }

    post {
        always {
            junit 'target/surefire-reports/*.xml'
        }
    }
}


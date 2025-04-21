pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/SrikanthMortha/java-maven-devops-pipeline.git'
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
                echo 'Push logic will be added once credentials are set.'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy step pending Kubernetes/infra readiness.'
            }
        }
    }

    post {
        always {
            archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
            junit 'target/surefire-reports/*.xml'
        }
    }
}


pipeline {
    agent any

    tools {
        maven 'Maven'
    }

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/Gowtham-52/automated-cicd-pipeline.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Archive Artifact') {
            steps {
                archiveArtifacts artifacts: 'target/*.war'
            }
        }

        stage('Deploy with Ansible') {
            steps {
                sh 'ansible-playbook ansible/deploy.yml'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t java-webapp:v1 .'
            }
        }

        stage('Docker Push') {
            steps {
                sh 'docker push your-dockerhub-username/java-webapp:v1'
            }
        }

        stage('Kubernetes Deployment') {
            steps {
                sh 'kubectl apply -f kubernetes/'
            }
        }
    }
}

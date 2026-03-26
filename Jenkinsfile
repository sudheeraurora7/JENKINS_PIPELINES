// File: Jenkinsfile
pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git 'https://github.com/YOUR_USERNAME/YOUR_REPO.git'
            }
        }

        stage('Build') {
            steps {
                sh 'javac /Main.java'
            }
        }

        stage('Run') {
            steps {
                sh 'java -cp src Main'
            }
        }
    }
}

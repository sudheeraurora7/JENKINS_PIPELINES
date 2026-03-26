// File: Jenkinsfile
pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git 'https://github.com/sudheeraurora7/JENKINS_PIPELINES.git'
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

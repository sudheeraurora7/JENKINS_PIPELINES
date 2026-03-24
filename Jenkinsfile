pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo "Checking files..."
                sh 'ls -l'
            }
        }

        stage('Deploy HTML') {
            steps {
                echo "Deploying HTML to server..."

                sh '''
                sudo mkdir -p /var/www/html
                sudo cp index.html /var/www/html/
                '''
            }
        }
    }
}

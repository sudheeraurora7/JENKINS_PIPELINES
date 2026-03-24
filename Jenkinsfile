pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo "Code already checked out by Jenkins"
            }
        }

        stage('Build') {
            steps {
                echo "Building project..."
                sh 'ls -l'
            }
        }

        stage('Deploy to EC2') {
            steps {
                echo "Deploying to EC2..."

                sh '''
                ssh -o StrictHostKeyChecking=no ubuntu@<YOUR-EC2-IP> "
                    mkdir -p /var/www/html &&
                    rm -rf /var/www/html/*"
                '''

                sh '''
                scp -o StrictHostKeyChecking=no index.html ubuntu@<YOUR-EC2-IP>:/var/www/html/
                '''
            }
        }
    }
}

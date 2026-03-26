// File: Jenkinsfile
pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/sudheeraurora7/JENKINS_PIPELINES.git'
            }
        }

        stage('Create HTML') {
            steps {
                sh '''
                mkdir -p site
                cat <<EOF > site/index.html
                <!DOCTYPE html>
                <html>
                <head>
                    <title>Jenkins Nginx</title>
                </head>
                <body>
                    <h1>🚀 Deployed via Jenkins Pipeline</h1>
                    <h2>Nginx Docker Running Successfully</h2>
                </body>
                </html>
                EOF
                '''
            }
        }

        stage('Deploy Nginx') {
            steps {
                sh '''
                docker stop nginx || true
                docker rm nginx || true

                docker run -d \
                  --name nginx \
                  -p 80:80 \
                  -v $(pwd)/site:/usr/share/nginx/html \
                  nginx
                '''
            }
        }
    }
}

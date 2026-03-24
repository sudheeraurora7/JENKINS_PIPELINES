pipeline {
    agent any

    stages {

        stage('Generate HTML') {
            steps {
                script {
                    def date = new Date().toString()

                    sh """
                    sed -e 's/__BUILD__/${BUILD_NUMBER}/g' \
                        -e 's/__DATE__/${date}/g' \
                        index.html > output.html
                    """
                }
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                sudo mkdir -p /var/www/html
                sudo cp output.html /var/www/html/index.html
                '''
            }
        }
    }
}

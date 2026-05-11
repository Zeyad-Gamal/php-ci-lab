pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Zeyad-Gamal/php-ci-lab.git'
            }
        }

        stage('Run Unit Tests') {
            steps {
                sh '/usr/local/bin/phpunit --log-junit results.xml tests/'
            }
        }

        stage('Display Results') {
            steps {
                junit 'results.xml'
            }
        }
    }

    post {

        always {
            echo 'Pipeline job finished.'
        }

        success {
            echo 'Congratulations! All tests passed successfully.'
        }

        failure {
            echo 'The code failed the tests! Please check the Test Result trend for details.'
        }
    }
}
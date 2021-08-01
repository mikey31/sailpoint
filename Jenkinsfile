pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                archive (includes: '*.html')
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }

        post {
            success {
                // publish html
                publishHTML target: [
                    allowMissing: false,
                    includes: '**/*',
                    alwaysLinkToLastBuild: true,
                    keepAll: true,
                    reportDir: '',
                    reportFiles: 'index.html',
                    reportName: 'RCov Report'
                    ]
                 }
            }
        }
    }
} 

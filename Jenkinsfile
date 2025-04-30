pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                // If using Git, replace with your repo URL
                // git 'https://github.com/your/repo.git'

                // Or create the HTML manually for the demo
                sh '''
                    mkdir -p reports
                    echo "<html><body><h1>Hello from Jenkins!</h1></body></html>" > reports/index.html
                '''
            }
        }

        stage('Publish HTML') {
            steps {
                publishHTML (target: [
                    allowMissing: false,
                    alwaysLinkToLastBuild: true,
                    keepAll: true,
                    reportDir: 'reports',
                    reportFiles: 'index.html',
                    reportName: 'My HTML Report'
                ])
            }
        }
    }
}

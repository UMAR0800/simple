pipeline {
    agent any 

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from the GitHub repository
                git url: 'https://github.com/UMAR0800/simple-python-app.git', credentialsId: 'github-token'
            }
        }
        
        stage('Install Dependencies') {
            steps {
                // Install dependencies
                echo 'Installing dependencies...'
                sh 'pip3 install -r requirements.txt' // Use pip3 for Python 3
            }
        }

        stage('Run Application') {
            steps {
                // Run the application
                echo 'Running application...'
                sh 'python3 app.py' // Use python3 for the application
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}

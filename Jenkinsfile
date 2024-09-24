pipeline {
    agent any 

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from the GitHub repository
                git url: 'https://github.com/umar0800/simple-python-app.git', credentialsId: 'github-token'
            }
        }
        
        stage('Install Dependencies') {
            steps {
                // Install dependencies
                echo 'Installing dependencies...'
                sh 'pip install -r requirements.txt' // Install requirements if there are any
            }
        }

        stage('Run Application') {
            steps {
                // Run the application
                echo 'Running application...'
                sh 'python app.py'
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

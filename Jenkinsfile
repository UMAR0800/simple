pipeline {
    agent any 

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from the GitHub repository
                git url: 'https://github.com/UMAR0800/simple-python-app.git', credentialsId: 'github-token'
            }
        }

        stage('Setup Virtual Environment') {
            steps {
                // Create a virtual environment
                sh 'python3 -m venv venv' // Create virtual environment
                sh '. venv/bin/activate'   // Activate the virtual environment
            }
        }

        stage('Install Dependencies') {
            steps {
                // Install dependencies
                echo 'Installing dependencies...'
                sh '. venv/bin/activate && pip install -r requirements.txt' // Use pip from the virtual environment
            }
        }

        stage('Run Application') {
            steps {
                // Run the application
                echo 'Running application...'
                sh '. venv/bin/activate && python app.py' // Use python from the virtual environment
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

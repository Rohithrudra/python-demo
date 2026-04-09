pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Rohithrudra/simple-python.git'
            }
        }

        stage('Verify Python') {
            steps {
                sh 'python3 --version'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh '''
                if [ -f requirements.txt ]; then
                    pip3 install -r requirements.txt
                else
                    echo "No requirements.txt found"
                fi
                '''
            }
        }

        stage('Run Application') {
            steps {
                sh '''
                if [ -f app.py ]; then
                    python3 app.py
                else
                    echo "app.py not found"
                fi
                '''
            }
        }
    }
}

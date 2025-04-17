pipeline{
    agent any
    
    stages {
        stage('Checkout Code') {
            steps {
                git url:'https://github.com/AMMUG143/new_repo.git', branch:'main'
            }
        }
        stage('Install Dependencies') {
            steps {
                bat '''
                    python -m venv venv
                    call venv\\Scripts\\activate
                    python -m pip install --upgrade pip
                    pip install pytest
                '''
            }
        }
        stage('Run Tests') {
            steps {
                bat '''
                    call venv\\Scripts\\activate
                    pytest test.py
                '''
            }
        }
        stage('Run Script') {
            steps {
                bat '''
                    call venv\\Scripts\\activate
                    python add.py
                '''
            }
        }
    }
}

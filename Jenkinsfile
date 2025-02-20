pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git 'https://github.com/Pravalikaa18/simple.git'
            }
        }

        stage('Run Python') {
            steps {
                sh 'python3 Pravalika_script.py'
            }
        }
    }
}

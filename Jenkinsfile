pipeline {
    agent any

    environment {
        GITHUB_REPO = 'https://github.com/Pravalikaa18/simple.git'  // URL of your GitHub repository
        GITHUB_CREDENTIALS = 'github-credentials-id'  // The credential ID you saved earlier
    }

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM',
                          branches: [[name: '*/master']],
                          userRemoteConfigs: [[url: GITHUB_REPO, credentialsId: GITHUB_CREDENTIALS]]])
            }
        }

        stage('Create Python Script') {
            steps {
                script {
                    // Create a simple Python script
                    writeFile file: 'pravalika_script.py', text: '''print("Hello, pravalika!")'''
                }
            }
        }

        stage('Run Python Script') {
            steps {
                script {
                    // Run the Python script
                    sh 'python3 pravalika_script.py'
                }
            }
        }

        stage('Commit and Push to GitHub') {
            steps {
                script {
                    // Configure Git user identity
                    sh 'git config --global user.email "pravalikapann987@gmail.com"'
                    sh 'git config --global user.name "Pravalikaa18"'
                    
                    // Add, commit, and push changes
                    sh 'git add pravalika_script.py'
                    sh 'git commit -m "Add pravalika script"'
                    sh 'git push origin master'
                }
            }
        }
    }
}

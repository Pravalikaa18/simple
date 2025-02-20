pipeline {
    agent any

    environment {
        GITHUB_REPO = 'https://github.com/Pravalikaa18/simple.git'  // Update with your repo URL
       // GITHUB_CREDENTIALS = 'github-credentials-id'  // Update with your GitHub credentials
    }

    stages {
        stage('Clone Repository') {
            steps {
                // Clone the repository from GitHub
                git url: "${GITHUB_REPO}"
            }
        }

        stage('Create Python Script') {
            steps {
                script {
                    // Create a Python script dynamically
                    def pythonScript = '''print("Hello, pravalika!")'''
                    writeFile(file: 'pravalika_script.py', text: pythonScript)
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
                    // Git commit and push the script back to GitHub
                    sh 'git add pravalika_script.py'
                    sh 'git commit -m "Add pravalika script"'
                    sh 'git push origin main'  // Ensure 'main' is your default branch name
                }
            }
        }
    }
}

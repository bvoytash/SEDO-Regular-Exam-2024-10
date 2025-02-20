pipeline {
    agent any 

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from the repository
                git 'https://github.com/your-repo/your-dotnet-project.git'
            }
        }

        stage('Restore') {
            steps {
                // Restore NuGet packages
                script {
                    bat 'dotnet restore'
                }
            }
        }

        stage('Build') {
            steps {
                // Build the project
                script {
                    bat 'dotnet build --configuration Release'
                }
            }
        }

        stage('Test') {
            steps {
                // Run tests
                script {
                    bat 'dotnet test'
                }
            }
        }

        stage('Publish') {
            steps {
                // Publish the application
                script {
                    bat 'dotnet publish --configuration Release --output ./publish'
                }
            }
        }

        stage('Deploy') {
            steps {
                // Deploy the application (customize this step based on your deployment strategy)
                script {
                    bat 'powershell -File deploy.ps1'
                }
            }
        }
    }

    post {
        success {
            echo 'Build and deployment succeeded!'
        }
        failure {
            echo 'Build or deployment failed.'
        }
    }
}

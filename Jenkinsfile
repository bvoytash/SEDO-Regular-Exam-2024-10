pipeline {
    agent any

    environment {
        DOTNET_VERSION = "6.0.x"
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Verify .NET Installation') {
            steps {
                script {
                    // Verify the .NET installation using the version command
                    sh 'dotnet --version'
                }
            }
        }

        stage('Restore dependencies') {
            steps {
                sh 'dotnet restore'
            }
        }

        stage('Build') {
            steps {
                sh 'dotnet build --no-restore'
            }
        }

        stage('Run Unit Tests') {
            steps {
                sh 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}

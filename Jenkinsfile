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

        stage('Setup .NET') {
            steps {
                script {
                    sh 'wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb'
                    sh 'sudo dpkg -i packages-microsoft-prod.deb'
                    sh 'rm packages-microsoft-prod.deb'
                    sh 'sudo apt-get update; sudo apt-get install -y dotnet-sdk-6.0'
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

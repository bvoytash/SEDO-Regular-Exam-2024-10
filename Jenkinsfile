pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        
        stage('Setup .NET') {
            steps {
                script {
                    def dotnetVersion = '6.0.x'
                    sh "export DOTNET_ROOT=\$HOME/.dotnet && export PATH=\$DOTNET_ROOT:\$PATH"
                    sh "wget https://dot.net/v1/dotnet-install.sh -O dotnet-install.sh"
                    sh "chmod +x dotnet-install.sh"
                    sh "./dotnet-install.sh --version ${dotnetVersion}"
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
                sh 'dotnet test HouseRentingSystem.UnitTests/HouseRentingSystem.UnitTests.csproj --no-build --verbosity normal'
            }
        }
    }
}

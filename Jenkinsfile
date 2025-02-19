pipeline {
    agent any
    
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
                sh 'dotnet test HouseRentingSystem.Tests/HouseRentingSystem.Tests.csproj --no-build --verbosity normal'
            }
        }
    }
}

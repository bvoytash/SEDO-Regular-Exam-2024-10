pipeline {
    agent any 

    stages {
        stage('Restore') {
            steps {
                script {
                    sh 'dotnet restore'
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    sh 'dotnet build --configuration Release'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    sh 'dotnet test'
                }
            }
        }
    }
}

pipeline {
    agent any

    stages {
        stage('Restore') {
            steps {
                script {
                    if (isUnix()) {
                        sh 'dotnet restore'
                    } else {
                        bat 'dotnet restore'
                    }
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    if (isUnix()) {
                        sh 'dotnet build --configuration Release'
                    } else {
                        bat 'dotnet build --configuration Release'
                    }
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    if (isUnix()) {
                        sh 'dotnet test'
                    } else {
                        bat 'dotnet test'
                    }
                }
            }
        }
    }
}

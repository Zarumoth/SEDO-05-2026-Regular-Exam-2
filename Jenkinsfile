pipeline {
    agent any

    stages {
        stage('Restore') {
            steps {
                sh 'dotnet restore'
            }
        }
        stage('Build') {
            steps {
                sh 'dotnet build --configuration Release'
            }
        }
        stage('Test') {
            when {
                branch 'main'
            }
            steps {
                sh 'dotnet test --configuration Release'
            }
        }
    }
}
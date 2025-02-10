pipeline {
    agent {
        docker { 
            image 'mcr.microsoft.com/dotnet/sdk:6.0' 
            label 'docker' 
        }
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Restore') {
            steps {
                sh 'dotnet restore'
            }
        }
        stage('Build') {
            steps {
                sh 'dotnet build'
            }
        }
        stage('Test') {
            steps {
                sh 'dotnet test'
            }
        }
    }
}

pipeline {
    agent any

    environment {
        // Define your environment variables (e.g., for .NET SDK if necessary)
        DOTNET_CLI_HOME = '/tmp'  // This is needed for environments like Jenkins to avoid permission issues
    }

    stages {
        stage('Restore') {
            steps {
                echo 'Restoring NuGet packages...'
                sh 'dotnet restore'  // Restore the NuGet packages
            }
        }

        stage('Build') {
            steps {
                echo 'Building the project...'
                sh 'dotnet build --configuration Release'  // Build the project in Release mode
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'dotnet test --configuration Release'  // Run tests in Release mode
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed. Check the logs for errors.'
        }
    }
}

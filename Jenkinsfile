pipeline {
    agent any
    
    stages {
        stage('Checkout Repository') {
            steps {
                checkout scm
            }
        }
        
        stage('Restore application dependencies') {
            steps {
                bat 'dotnet restore'
            }
        }
        
        stage('Build') {
            steps {
                bat 'dotnet build --no-restore'
            }
        }
        
        stage('Test') {
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
    
    post {
        always {
            echo "Pipeline finished successfully"
        }
    }
}

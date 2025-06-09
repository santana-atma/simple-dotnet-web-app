pipeline {
    agent any
    environment {
    PATH = "/usr/local/share/dotnet:$PATH"
       }
    stages {
        stage('Build') { 
            steps {
                sh 'dotnet restore' 
                sh 'dotnet build --no-restore' 
            }
        }
    }
}
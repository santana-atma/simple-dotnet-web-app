pipeline {
    agent any
    stages {
        stage('Build') { 
            steps {
                export PATH=/usr/local/share/dotnet:$PATH
                sh 'dotnet restore' 
                sh 'dotnet build --no-restore' 
            }
        }
    }
}
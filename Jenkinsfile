pipeline {
    agent any
    environment {
    PATH = "/usr/local/share/dotnet:$PATH"
       }
    stages {
        stage('Build') { 
            steps {
                bash 'dotnet restore' 
                bash 'dotnet build --no-restore' 
            }
        }
    }
}
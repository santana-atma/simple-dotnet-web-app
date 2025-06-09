pipeline {
    agent any
    environment {
    PATH = "/usr/local/share/dotnet:$PATH"
       }
    stages {
        stage('Build') { 
            steps {
                sh 'which dotnet'
                sh 'dotnet restore' 
                sh 'dotnet build --no-restore' 
            }
        }
    }
}
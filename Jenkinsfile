pipeline {
    agent any
    environment {
    PATH = '/usr/local/share/dotnet:${env.PATH}'
       }
    stages {
        stage('Build') { 
            steps {
                echo 'PATH is: ${env.PATH}'
                sh 'dotnet restore' 
                sh 'dotnet build --no-restore' 
            }
        }
    }
}
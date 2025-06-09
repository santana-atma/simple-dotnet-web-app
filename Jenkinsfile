//Jenkinsfile (Declarative Pipeline)
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'echo "Building SDK"'
                sh '''
                    export DOTNET_SYSTEM_GLOBALIZATION_INVARIANT=1
                    /usr/local/share/dotnet/dotnet restore
                    /usr/local/share/dotnet/dotnet build --no-restore
                '''
            }
        }
        stage('Test') { 
            steps {
                sh '/usr/local/share/dotnet/dotnet test --no-build --no-restore --collect "XPlat Code Coverage"'
            }
            post {
                always {
                    recordCoverage(tools: [[parser: 'COBERTURA', pattern: '**/*.xml']], sourceDirectories: [[path: 'SimpleWebApi.Test/TestResults']])
                }
            }
        }
        stage('Deliver') { 
            steps {
                sh '/usr/local/share/dotnet/dotnet publish SimpleWebApi --no-restore -o published' 
            }
            post {
                success {
                    archiveArtifacts 'published/*.*'
                }
            }
        }
    }
}
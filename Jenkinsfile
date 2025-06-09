pipeline {
    agent any
    stages {
        stage('Install SDK'){
            steps {
                sh 'apt install wget'
                sh 'cd ~'
                sh 'wget https://builds.dotnet.microsoft.com/dotnet/Sdk/8.0.410/dotnet-sdk-8.0.410-linux-x64.tar.gz'
                sh 'DOTNET_FILE=dotnet-sdk-8.0.410-linux-x64.tar.gz'
                sh 'export DOTNET_ROOT=$(pwd)/.dotnet'
                sh 'mkdir -p "$DOTNET_ROOT" && tar zxf "$DOTNET_FILE" -C "$DOTNET_ROOT"'
                sh 'export PATH=$PATH:$DOTNET_ROOT:$DOTNET_ROOT/tools'

            }
        }
        stage('Build') { 
            steps {
                sh 'dotnet restore' 
                sh 'dotnet build --no-restore' 
            }
        }
    }
}
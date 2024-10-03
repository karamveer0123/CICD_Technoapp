pipeline {
    agent any
    stages {
        stage('restore') {
            steps {
                sh '/var/lib/jenkins/dotnet/dotnet restore "technosavvy.mAPI/technosavvy.mAPI.csproj"'
            }
        }
        stage('build') {
            steps {
                sh '/var/lib/jenkins/dotnet/dotnet build "technosavvy.mAPI/technosavvy.mAPI.csproj" -c release -o ./bin/build'
            }
        }
        stage('publish') {
            steps {
                sh '/var/lib/jenkins/dotnet/dotnet publish "technosavvy.mAPI/technosavvy.mAPI.csproj" -c release -o ./bin/publish'
            }
        }
    }
}
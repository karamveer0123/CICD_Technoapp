pipeline {
    agent any
    triggers {
        // GitHub trigger example
        githubPush() // This will listen for pushes to the repository
    }
    stages {
        stage('restore') {
            steps {
                sh 'echo "Restoring the Project"'
                sh '/var/lib/jenkins/dotnet/dotnet restore "Technosavvy.mAPI/technosavvy.mAPI.csproj"'
                }
            }
        }
        stage('build') {
            steps {
                sh '/var/lib/jenkins/dotnet/dotnet build "Technosavvy.mAPI/technosavvy.mAPI.csproj" -c release -o ./bin/build'
            }
        }
        stage('publish') {
            steps {
                sh '/var/lib/jenkins/dotnet/dotnet publish "Technosavvy.mAPI/technosavvy.mAPI.csproj" -c release -o ./bin/publish'
            }
        }
    }
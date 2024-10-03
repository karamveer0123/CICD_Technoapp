pipeline {
    stages {
        stage('restore') {
            steps {
                sh 'dotnet restore "technosavvy.mAPI/technosavvy.mAPI.csproj"'
            }
        }
        stage('build') {
            steps {
                sh 'dotnet build "technosavvy.mAPI/technosavvy.mAPI.csproj" -c release -o ./bin/build'
            }
        }
        stage('publish') {
            steps {
                sh 'dotnet publish "technosavvy.mAPI/technosavvy.mAPI.csproj" -c release -o ./bin/publish'
            }
        }
    }
}
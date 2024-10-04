pipeline {
    agent any
    triggers {
        // GitHub trigger for listening to pushes to the repository
        githubPush()
    }
    stages {
        stage('Restore') {
            steps {
                script {
                    echo "Restoring the Project"
                    sh '/var/lib/jenkins/dotnet/dotnet restore "Technosavvy.mAPI/technosavvy.mAPI.csproj"'
                }
            }
        }
        stage('Build') {
            steps {
                script {
                    echo "Building the Project"
                    sh '/var/lib/jenkins/dotnet/dotnet build "Technosavvy.mAPI/technosavvy.mAPI.csproj" -c Release -o ./bin/build'
                }
            }
        }
        stage('Publish') {
            steps {
                script {
                    echo "Publishing the Project"
                    sh '/var/lib/jenkins/dotnet/dotnet publish "Technosavvy.mAPI/technosavvy.mAPI.csproj" -c Release -o ./bin/publish'
                }
            }
        }
    }
    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed. Please check the logs.'
        }
    }
}

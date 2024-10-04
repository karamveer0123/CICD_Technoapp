pipeline {
    agent any
    triggers {
        // GitHub trigger for listening to pushes to the repository
        githubPush()
    }
    stages {
        stage('Restore_mapi') {
            steps {
                script {
                    echo "Restoring the Project"
                    sh '/var/lib/jenkins/dotnet/dotnet restore "Technosavvy.mAPI/technosavvy.mAPI.csproj"'
                }
            }
        }
        stage('Build_mapi') {
            steps {
                script {
                    echo "Building the Project"
                    sh '/var/lib/jenkins/dotnet/dotnet build "Technosavvy.mAPI/technosavvy.mAPI.csproj" -c Release -o ./Technosavvy.mAPI/bin/build'
                }
            }
        }
        stage('Publish_mapi') {
            steps {
                script {
                    echo "Publishing the Project"
                    sh '/var/lib/jenkins/dotnet/dotnet publish "Technosavvy.mAPI/technosavvy.mAPI.csproj" -c Release -o ./Technosavvy.mAPI/bin/publish'
                }
            }
        }
        stage('Restore_webui') {
            steps {
                script {
                    echo "Restoring the Project"
                    sh '/var/lib/jenkins/dotnet/dotnet restore "Technosavvy.webui/technosavvy.webui.csproj"'
                }
            }
        }
        stage('Build_webui') {
            steps {
                script {
                    echo "Building the Project"
                    sh '/var/lib/jenkins/dotnet/dotnet build "Technosavvy.webui/technosavvy.webui.csproj" -c Release -o ./Technosavvy.mAPI/bin/build'
                }
            }
        }
        stage('Publish_webui') {
            steps {
                script {
                    echo "Publishing the Project"
                    sh '/var/lib/jenkins/dotnet/dotnet publish "Technosavvy.webui/technosavvy.webui.csproj" -c Release -o ./Technosavvy.mAPI/bin/publish'
                }
            }
        }
        stage('Restore_watcher') {
            steps {
                script {
                    echo "Restoring the Project"
                    sh '/var/lib/jenkins/dotnet/dotnet restore "Technosavvy.watcher/technosavvy.watcher.csproj"'
                }
            }
        }
        stage('Build_watcher') {
            steps {
                script {
                    echo "Building the Project"
                    sh '/var/lib/jenkins/dotnet/dotnet build "Technosavvy.watcher/technosavvy.watcher.csproj" -c Release -o ./Technosavvy.mAPI/bin/build'
                }
            }
        }
        stage('Publish_watcher') {
            steps {
                script {
                    echo "Publishing the Project"
                    sh '/var/lib/jenkins/dotnet/dotnet publish "Technosavvy.watcher/technosavvy.watcher.csproj" -c Release -o ./Technosavvy.mAPI/bin/publish'
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

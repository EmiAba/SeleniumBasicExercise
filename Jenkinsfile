pipeline    
{
    agent any

    stages {
        stage('Restore dependencies') {
            steps {
               bat 'dotnet restore'
            }
            post {
                always {
                    echo 'Step executed successfully'
                }
            }
        }
        stage('Build solution') {
            steps {
                bat 'dotnet build --no-restore' 
                
            }
        }
        stage('Run tests for project 1') {
            steps {
                bat 'dotnet test TestProject1/TestProject1.csproj --no-build --verbosity normal'
            }
        }
         stage('Run tests for project 2') {
            steps {
                bat 'dotnet test TestProject2/TestProject2.csproj --no-build --verbosity normal'
            }
        }
         stage('Run tests for project 3') {
            steps {
                bat 'dotnet test TestProject3/TestProject3.csproj --no-build --verbosity normal'
            }
        }
    }
    post {
        always {
            echo 'Workflow completed successfully'
        }
    }
}

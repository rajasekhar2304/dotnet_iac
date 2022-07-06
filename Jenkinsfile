pipeline {
    agent any   
    
    stages {
        stage("SCM Checkout") {
            steps {                
                git branch: 'master', 
                    credentialsId: 'RajaGithubAccess',
                    url: 'https://github.com/rajasekhar2304/dotnetApp.git'
                
                dir("dotnet_iac") {
                    git branch: 'master',
                        credentialsId: 'RajaGithubAccess',
                        url: 'https://github.com/rajasekhar2304/dotnet_iac.git'
                }
            }
        }
        stage("Build") {
            steps {
                sh "dotnet clean"
                sh "dotnet build"
            }
        }
    }
}    
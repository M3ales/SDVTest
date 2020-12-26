#!/usr/bin/env groovy

pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building'
                sh 'nuget restore SDVTest.sln'
                sh "dotnet msbuild SDVTest.sln /p:Configuration=Release /p:Platform=\"Any CPU\" /p:ProductVersion=1.0.0.${env.BUILD_NUMBER}"
            }
        }
    }
    post {
        always {
        archive 'SDVTest/bin/Release/**'
        }
    }
}
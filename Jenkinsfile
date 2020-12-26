#!/usr/bin/env groovy

pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building'
                sh 'nuget restore SDVTest.sln'
                sh "dotnet build"
            }
        }
    }
    post {
        always {
        archive 'SDVTest/bin/Release/**'
        }
    }
}
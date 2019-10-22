pipeline {
  agent any
  stages {
    stage('hello world') {
      parallel {
        stage('Hello world on Windows') {
            agent {
              docker {
              label 'Windows&&Docker&&aws'
              image 'mcr.microsoft.com/powershell:preview'
              }
          } 
          options {
            timeout(1) // in case the pipeline hangs
          }

          steps {
    //        echo "Hello world using a Jenkins Command"
            powershell 'Write-Host "Hello World, from Powershell"'

          }
        }
        stage('Hello world on Linux') {
            agent {
              docker {
              label 'Linux&&Docker&&aws'
              image 'alpine:latest'
              }
          } 
          options {
            timeout(1) // in case the pipeline hangs
          }

          steps {
    //        echo "Hello world using a Jenkins Command"
            sh 'echo "hello world"'

          }
        }
      }
    }
}

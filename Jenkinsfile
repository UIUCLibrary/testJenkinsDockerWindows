pipeline {
  agent any
  stages {
    stage('hello world') {
      parallel {
        stage('Hello world on Windows') {
            agent {
              docker {
              label 'Windows&&Docker&&aws'
              image 'mcr.microsoft.com/windows/servercore:ltsc2019'
              }
          } 
          options {
            timeout(2) // in case the pipeline hangs
          }

          steps {
            powershell 'powershell "cmd /c echo test inside"'

          }
        }
        stage('Hello world on Linux') {
            agent {
              docker {
              label 'linux&&docker&&aws'
              image 'alpine:latest'
              }
          } 
          options {
            timeout(2) // in case the pipeline hangs
          }

          steps {
            sh 'echo "hello world"'

          }
        }
      }
    }
  }
}

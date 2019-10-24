pipeline {
  agent any
  stages {
    stage('hello world') {
      parallel {
        stage('Hello world on Windows') {
            agent {
              docker {
              label 'Windows&&Docker&&aws'
              image 'python:3.7'
              }
          } 
          options {
            timeout(2) // in case the pipeline hangs
          }

          steps {
            bat "python --version"

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

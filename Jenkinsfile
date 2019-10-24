pipeline {
  agent none
  stages {
    stage('hello world') {
      parallel {
        stage('Hello world on Windows') {
            agent {
              label 'Windows&&Docker&&aws'
              // docker {
              // label 'Windows&&Docker&&aws'
              // image 'python:3.7'
              // }
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
              image 'ubuntu:latest'
              }
          } 
          options {
            timeout(2) // in case the pipeline hangs
          }

          steps {
            sh 'ls'

          }
        }
      }
    }
  }
}

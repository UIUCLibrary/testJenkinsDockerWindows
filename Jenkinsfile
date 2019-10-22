pipeline {
  agent any
  stages {
    stage('hello world') {
      parallel {
        stage('Hello world on Windows') {
            agent {
              docker {
              label 'Windows&&Docker&&aws'
              image 'tyko/master'
              }
          } 
          options {
            timeout(1) // in case the pipeline hangs
          }

          steps {
            cmake 'InSearchPath'

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
            timeout(1) // in case the pipeline hangs
          }

          steps {
            sh 'echo "hello world"'
            cmake 'InSearchPath'

          }
        }
      }
    }
  }
}

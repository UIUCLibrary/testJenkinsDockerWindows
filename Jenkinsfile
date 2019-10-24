pipeline {
  agent none
  stages {
    stage('hello world') {
      parallel {
        stage('Hello world on Windows') {
          agent {
            dockerfile {
              filename 'Dockerfile'
            }
          }

          //   agent {

          //      docker {
          //         label 'Windows&&Docker&&aws'
          //         image 'python:3.7'
          //      }
          // } 
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
              image 'alpine'
              label 'linux&&Docker&&aws'
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

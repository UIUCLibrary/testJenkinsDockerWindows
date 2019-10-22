pipeline {
  agent {
        docker {
        label 'Windows&&Docker&&aws'
        image 'mcr.microsoft.com/powershell'
        }
    }
  stages {
    stage('Hello world') {
        
      options {
        timeout(1) // in case the pipeline hangs
      }

      steps {
        echo "Hello world using a Jenkins Command"
        powershell 'Write-Host "Hello World, from Powershell"'   
      }
    }
  }
}
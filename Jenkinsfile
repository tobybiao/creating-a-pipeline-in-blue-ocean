pipeline {
  agent {
    docker {
      image 'node:8.16.2-alpine'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'npm  --registry https://registry.npm.taobao.org install'
      }
    }

    stage('Test') {
      environment {
        CI = 'true'
      }
      steps {
        sh './jenkins/scripts/test.sh'
      }
    }

    stage('Deliver') {
      steps {
        sh './jenkins/scripts/deliver.sh'
        input 'Finished using the web site? (Click "Proceed" to continue)'
        sh './jenkins/scripts/kill.sh'
      }
    }

  }
}
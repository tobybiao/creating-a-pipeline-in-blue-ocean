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

  }
}
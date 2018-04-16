pipeline {
  agent any
  stages {
    stage('test') {
      steps {
        echo 'update docker'
      }
    }
    stage('update dockerfile') {
      steps {
        sh '/bin/bash /opt/dockerrun.sh'
      }
    }
  }
}
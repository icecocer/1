pipeline {
  agent any
  stages {
    stage('test') {
      steps {
        echo 'update docker'
      }
    }
    stage('hello') {
      steps {
        script {
          node {
            echo 'ls /opt/'
          }
        }

      }
    }
  }
}
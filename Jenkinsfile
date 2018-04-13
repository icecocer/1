pipeline {
  agent any
  stages {
    stage('test') {
      steps {
        echo 'update docker'
      }
    }
    stage('show /opt') {
      steps {
        script {
          node {
            sh 'ls /opt/'
          }
        }

      }
    }
    stage('update dokcer') {
      steps {
        script {
          node {
            sh 'sh /opt/dockerrun.sh'
          }
        }

      }
    }
    stage('test2') {
      steps {
        script {
          node {
            echo 'test2'
     }
    }
  }
}

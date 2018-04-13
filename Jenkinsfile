pipeline {
  agent any
  stages {
    stage('test') {
      steps {
        echo 'update docker'
      }
    }
    stage('show /opt') {
      parallel {
        stage('show /opt') {
          steps {
            script {
              node {
                sh 'ls /opt/'
              }
            }

          }
        }
        stage('show /') {
          steps {
            echo 'test'
          }
        }
        stage('2') {
          steps {
            retry(count: 2) {
              sh 'ls /opt'
            }

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
    stage('time') {
      steps {
        timeout(time: 1, unit: 'MINUTES') {
          sh 'date'
        }

      }
    }
  }
}
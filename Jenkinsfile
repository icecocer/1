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
        stage('1') {
          steps {
            script {
              node {
                sh 'ls /opt/'
              }
            }

          }
        }
        stage('2') {
          steps {
            echo 'test'
          }
        }
        stage('3') {
          steps {
            retry(count: 2) {
              sh 'ls /opt'
            }

          }
        }
        stage('4') {
          steps {
            node(label: 'node2') {
              sh 'ls /opt/'
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
    stage('Email') {
      steps {
        mail(subject: '$DEFAULT_SUBJECT', body: '$DEFAULT_POSTSEND_SCRIPT', cc: '$DEFAULT_CONTENT', to: '543266565@qq.com', replyTo: '543266565@qq.com')
      }
    }
  }
}
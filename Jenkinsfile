pipeline {
  agent any
  stages {
    stage('start') {
      steps {
        sh 'echo "start sample pipeline"'
        sh 'echo "start second step"'
      }
    }
    stage('para1') {
      parallel {
        stage('para1') {
          steps {
            sh 'echo "para1start"'
            sh 'echo "para1end"'
          }
        }
        stage('para2') {
          steps {
            sh 'echo "para2start"'
            sh 'echo "para2 end"'
            sh 'exit 0'
          }
        }
      }
    }
    stage('useENV') {
      environment {
        AAAA = 'message'
      }
      steps {
        sh 'echo "${AAAA}"'
      }
    }
    stage('end') {
      steps {
        sh 'echo "end pipeline"'
      }
    }
  }
}
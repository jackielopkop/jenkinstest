pipeline {
  agent any
  stages {
    stage('prep') {
      parallel {
        stage('prep') {
          environment {
            version = '1'
          }
          steps {
            sleep 3
            echo 'hello version'
            dir(path: '/home')
          }
        }

        stage('check') {
          steps {
            echo 'done!'
          }
        }

      }
    }

    stage('build') {
      steps {
        echo 'building'
      }
    }

    stage('deploy') {
      steps {
        sh 'pwd'
        sleep 2
      }
    }

    stage('test') {
      steps {
        sh 'python -V'
        echo 'testing finished'
      }
    }

  }
}
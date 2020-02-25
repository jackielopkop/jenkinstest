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
            bat 'echo hello'
            build 'Job1'
          }
        }

        stage('check') {
          environment {
            tomcatstatus = '1'
          }
          steps {
            echo 'checking some service${tomcatstatus}'
          }
        }

      }
    }

    stage('build&deploy') {
      steps {
        node(label: 'allocate-nodes') {
          dir(path: 'D:/') {
            bat 'cd D:/'
          }

        }

      }
    }

    stage('test') {
      steps {
        echo 'testing'
      }
    }

  }
}
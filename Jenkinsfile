pipeline {
  agent none
  stages {
    stage('Build') {
      agent {
        node {
          label 'java 8'
        }

      }
      steps {
        input(message: 'Deploy to Stage', ok: 'Yes')
        unstash 'Java 8'
      }
    }

    stage('Deploy to Staging') {
      parallel {
        stage('Deploy to Staging') {
          agent {
            node {
              label 'java 8'
            }

          }
          steps {
            sh 'echo my work'
            stash 'Java 8'
          }
        }

        stage(' Build Java 7') {
          agent {
            node {
              label 'Java 7'
            }

          }
          steps {
            echo 'hello'
          }
        }

        stage(' Build Java 8') {
          agent {
            node {
              label 'Java 8'
            }

          }
          steps {
            echo 'heelo'
          }
        }

      }
    }

  }
}
pipeline {
  agent any
  stages {
    stage('PREPARE') {
      steps {
        echo 'Preparing...'
      }
    }

    stage('CHECKOUT') {
      steps {
        echo 'Cloning...'
      }
    }

    stage('BUILD') {
      steps {
        echo 'Maven building'
      }
    }

    stage('UNIT TESTING') {
      steps {
        echo 'Unit testing'
      }
    }

    stage('CODE COVERAGE') {
      steps {
        echo 'Code coverage'
      }
    }

    stage('SONAR REPORT') {
      steps {
        echo 'Sonar'
      }
    }

    stage('UPLOAD') {
      steps {
        echo 'Artifact Uploading...'
      }
    }

    stage('POST ACTION') {
      steps {
        echo 'Sending mail and cleanup'
      }
    }

    stage('DEV-DEPLOY') {
      parallel {
        stage('DEV-DEPLOY') {
          steps {
            echo 'Deploying in DEV environment '
          }
        }

        stage('INT-DEPLOY') {
          steps {
            echo 'Deploying in INT environment '
          }
        }

        stage('UAT-DEPLOY') {
          steps {
            echo 'Deploying in UAT Environment '
          }
        }

        stage('PRO-DEPLOY') {
          steps {
            echo 'Deploying in PRO environment '
          }
        }

      }
    }

  }
}
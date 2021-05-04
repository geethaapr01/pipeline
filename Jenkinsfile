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

    stage('QUALITY CHECK') {
      parallel {
        stage('UNIT TESTING') {
          steps {
            echo 'Unit testing'
          }
        }

        stage('COVERAGE') {
          steps {
            echo 'Code Coverage...'
          }
        }

        stage('SONAR') {
          steps {
            echo 'Sonar reporting...'
          }
        }

        stage('HTML') {
          steps {
            echo 'Code quality Check...'
          }
        }

        stage('CUCUMBER') {
          steps {
            echo 'Cucumber reporting...'
          }
        }

        stage('JACOCO') {
          steps {
            echo 'Jacoco reporting...'
          }
        }

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

	stage('DOWNLOAD') {
      steps {
        echo 'Artifact Downloading...'
      }
    }
    stage('DEV-DEPLOY') {
      parallel {
        stage('DEV-DEPLOY') {
          steps {
            echo 'Deploying in DEV environment '
          }
        }

        stage('DEV-TESTING') {
          steps {
            echo 'Testing in DEV environment '
          }
        }

      }
    }

    stage('INT-DEPLOY') {
      parallel {
        stage('INT-DEPLOY') {
          steps {
            echo 'Deploying in INT'
          }
        }

        stage('INT TESTING') {
          steps {
            echo 'Testing in INT environment '
          }
        }

      }
    }

    stage('UAT-DEPLOY') {
      parallel {
        stage('UAT-DEPLOY') {
          steps {
            echo 'Deploying in UAT'
          }
        }

        stage('UAT-TESTING') {
          steps {
            echo 'Testing in UAT environment '
          }
        }

      }
    }

    stage('PRO-DEPLOY') {
      steps {
        echo 'Deploying in PRO'
      }
    }

  }
}
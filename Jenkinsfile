pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'Build .Net Application'
          }
        }

        stage('Test') {
          steps {
            echo 'Testing Application'
          }
        }

      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploying App to Host'
      }
    }

  }
}
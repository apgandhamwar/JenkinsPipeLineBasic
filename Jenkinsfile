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
            echo "Get Chrome Driver Path ${ChromeDriverPath}"
          }
        }

      }
    }

    stage('Deploy') {
      steps {
        input(message: 'Do you want to deploy?', id: 'Ok')
        echo 'Deploying App to Host'
      }
    }

  }
  environment {
    ChromeDriverPath = 'C:\\JenkinsHome'
  }
}
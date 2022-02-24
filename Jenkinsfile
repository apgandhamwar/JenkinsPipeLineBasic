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
        echo 'Deploying App to Host'
      }
    }

  }
  environment {
    ChromeDriverPath = 'C:\\JenkinsHome'
  }
}
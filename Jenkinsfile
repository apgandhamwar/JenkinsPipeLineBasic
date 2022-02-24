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

        stage('Test Log') {
          steps {
            writeFile(file: 'Test.txt', text: 'This is testing file')
          }
        }

      }
    }

    stage('Deploy') {
      parallel {
        stage('Deploy') {
          steps {
            input(message: 'Do you want to deploy?', id: 'Ok')
            echo 'Deploying App to Host'
          }
        }

        stage('Artifact') {
          steps {
            archiveArtifacts 'Test.txt'
          }
        }

      }
    }

  }
  environment {
    ChromeDriverPath = 'C:\\JenkinsHome'
  }
}
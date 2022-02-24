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
          environment {
            LocalVar = 'Hello All'
          }
          steps {
            writeFile(file: 'Test.txt', text: " ${LocalVar} This is testing file")
          }
        }

      }
    }

    stage('Deploy') {
      parallel {
        
        when {
           branch 'master'
        }
        stage('Deploy') {
          steps {
            input(message: 'Do you want to Deploy?', id: 'Ok')
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
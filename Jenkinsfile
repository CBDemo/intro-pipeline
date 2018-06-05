pipeline {
  agent any
  stages {
    stage('PreCheck') {
      steps {
        echo 'Continuing with deployment'
      }
    }
    stage('Checkout') {
      parallel {
        stage('Checkout') {
          steps {
            sh 'echo "Code checkout happen here"'
            echo "Hello ${params.Name}!"
            sh 'echo $MY_CREDENTIALS_USR'
            sh 'echo $MY_CREDENTIALS_PSW'
            sh 'java -version'
          }
        }
        stage('Validate') {
          steps {
            sh 'echo validate'
          }
        }
      }
    }
    stage('Build') {
      input {
        message 'Should we continue?'
      }
      steps {
        sh 'echo build'
      }
    }
    stage('Deploy') {
      steps {
        sh 'echo deploy'
      }
    }
  }
  environment {
    MY_NAME = 'Suresh'
    MY_CREDENTIALS = credentials('MyCreds')
  }
  parameters {
    string(name: 'Name', defaultValue: 'whoever you are', description: 'Who should I say hi to?')
  }
}
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
      steps {
        sh 'echo build'
      }
    }
    stage('Deploy') {
      options {
        timeout(time: 30, unit: 'SECONDS')
      }
      input {
        message 'suresh, Should we continue?'
        id 'Deploy'
        parameters {
          choice(name: 'APP_VERSION', choices: '''v1.1
v1.2
v1.3''', description: 'What to deploy?')
        }
      }
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
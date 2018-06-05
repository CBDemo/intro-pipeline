pipeline {
  agent {
    label 'jdk9'
  }
  stages {
    stage('Checkout') {
      parallel {
        stage('Checkout') {
          steps {
            sh 'echo "Code checkout happen here"'
            sh 'echo ${params.NAME}'
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
    string(name: 'NAME', defaultValue: 'whoever you are', description: 'who should i say hi to?')
  }
}
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
            sh 'echo $MY_NAME'
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
  }
}
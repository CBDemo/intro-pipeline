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
}
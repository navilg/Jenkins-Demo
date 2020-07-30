pipeline {
  agent any
  stages {
    stage('Compile') {
      steps {
        sh 'gcc main.cpp -o main.o'
      }
    }
    stage('Permission') {
      steps {
        sh 'chmod +x main.o'
      }
    }
    stage('Execute') {
      steps {
        sh './main.o'
      }
    }
  }
}

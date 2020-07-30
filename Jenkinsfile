pipeline {
  agent any
  stages {
    stage('install gcc') {
      steps {
        sh 'apt install gcc -y'
      }
    }
    stage('Compile') {
      steps {
        sh 'gcc sample.cpp -o sample.o'
      }
    }
    stage('Permission') {
      steps {
        sh 'chmod +x sample.o'
      }
    }
    stage('Execute') {
      steps {
        sh './sample.o'
      }
    }
  }
}

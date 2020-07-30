pipeline {
  agent any
  stages {
    stage('Compile') {
      steps {
        sh 'g++ sample.cpp -o sample.o'
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
    stage('Archive') {
      steps {
        archiveArtifacts 'sample.cpp, sample.o'
      }
    }
  }
}

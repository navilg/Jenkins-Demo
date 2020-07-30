pipeline {
  agent any
  ws('/home/ubuntu/') {
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
      stage('Parallel job') {
        parallel {
          stage('Build another job') {
            steps {
              build 'mvn-compile'
            }
          }
          stage('Print message') {
            steps {
              sh 'echo Test parallel job'
            }
          }
        }
      }
      stage('Clean Workspace') {
        steps {
          cleanWs()
        }
      }
    }
  }
}

pipeline {
  agent any
  stages {
    stage('myStage-Test'){
      steps {
        sh 'ls -la' 
      }
    }
    stage('Build') {
      steps { 
        sh 'ls' 
      }
    }
    stage('Deliver for development') {
      when {
        branch 'development'
      }
      steps {
        sh 'ls'
      }
    }
    stage('Deploy for production') {
      when {
        branch 'production'
      }
      steps {
        sh 'ls'
      }
    }
    stage('Deploy for release/*') {
      when {
        branch 'release/*'
      }
      steps {
        sh 'ls'
      }
    }
  }
}
pipeline {
  agent any
  stages {
    stage('myStage-Test'){
      steps {
        sh 'ls -la' 
        echo "GIT_COMMIT is ${env.GIT_COMMIT}"
        echo "GIT_COMMIT[0..7] is ${env.GIT_COMMIT[0..7]}"
        echo "BUILD_ID is ${env.BUILD_ID}"
      }
    }
    stage('Build') {
      agent any
      when {
        beforeAgent true
        branch 'release/*'
      }
      steps {
        sh """
          docker build \
              -f ./Dockerfile \
              -t digi/digi-web:latest \
              -t digi/digi-web:${env.GIT_COMMIT[0..7]} \
              .
        """
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
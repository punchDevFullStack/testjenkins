pipeline {
  agent any
  stages {
    // stage('Test') {
    //         agent {
    //             dockerfile {
    //                 dir 'scripts/agents'
    //             }
    //         }
    //         when {
    //             beforeAgent true
    //             branch 'master'
    //         }
    //         steps {
    //             sh 'ls' 
    //             sh 'echo env.BRANCH_NAME'  
    //         }
    //     }
    // stage('Build') {
    //   agent any
    //   when {
    //     beforeAgent true
    //     branch 'release/*'
    //   }
    //   steps {
    //     sh """
    //       docker build \
    //           -f ./Dockerfile \
    //           -t digi/digi-web:latest \
    //           -t digi/digi-web:${env.GIT_COMMIT[0..7]} \
    //           .
    //     """
    //   }
    // }
    // stage('Deliver for development') {
    //   when {
    //     branch 'development'
    //   }
    //   steps {
    //     sh 'ls'
    //   }
    // }
    // stage('Deploy for production') {
    //   when {
    //     branch 'production'
    //   }
    //   steps {
    //     sh 'ls'
    //   }
    // }
    stage('Deploy for release/*') {
      steps {
        sh 'ls'
        sh 'echo Branch Name: $BRANCH_NAME'
      }
    }
  }
}
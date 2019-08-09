pipeline {
  agent any
  stages {
    stage('Test') {
            agent {
                dockerfile {
                    dir 'scripts/agents'
                    args """
                        -v /home/pcr/workspace/build_cache/pcr-web/node_modules:/root/workspace/pcr-web/node_modules
                        -v /home/pcr/workspace/pcr-reports:/root/workspace/pcr-reports
                    """
                }
            }
            when {
                beforeAgent true
                branch 'master'
            }
            steps {
                sh 'ls'   
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
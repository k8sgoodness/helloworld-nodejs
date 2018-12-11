pipeline {
  agent none
  stages {
    stage('Say Hello') {
      agent { label 'nodejs-app' }
      steps {
        echo 'Hello World!'   
        sh 'node -version'
      }
    }
    stage('Deploy') {
      when {
        beforeAgent true
        branch 'master'
      }
      options {
        timeout(time: 30, unit: 'SECONDS') 
      }
      input {
        message "Should we continue?"
      }
      steps {
        echo "Continuing with deployment"
      }
    }
  }
}

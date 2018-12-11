pipeline {
    agent { label 'nodejs-app' }
  stages {
    stage('Say Hello') {
      steps {
        echo 'Hello World!'   
        sh 'node -version'
      }
    }
  }
}

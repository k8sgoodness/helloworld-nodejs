pipeline {
  agent none
  stages {
    stage('Say Hello') {
      agent { label 'nodejs-app' }
      steps {
        container('nodejs') {
          echo 'Hello World!'   
          sh 'node --version'
        }
      }
    }
    stage('Deploy') {
      when {
        beforeAgent true
        branch 'master'
      }
      options {
        timeout(time: 60, unit: 'SECONDS') 
      }
      input {
        message "Should we deploy?"
        submitter "sroskelley,roskelleycj"
        submitterParameter "APPROVER"
      }
      steps {
        echo "Continuing with deployment"
      }
    }
  }
}
#hello

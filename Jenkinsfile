pipeline {
  environment {
    //This variable need be tested as string
    doError = ‘1’
  }
  agent any
  stages {
    stage(‘Error’) {
      when {
        expression { doError == ‘1’ }
      }
      steps {
        echo “Failure”
        error “failure test. It’s work”
      }
    }
    stage(‘Success’) {
      when {
        expression { doError == ‘0’ }
      }
      steps {
        echo “ok”
      }
    }
  }
  post {
    always {
      echo ‘I will always execute’
    }
  post {
    success {
      mail to: naresh.manojari@gmail.com, subject: 'The Pipeline success'
    }
  }
}

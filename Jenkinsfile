pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Hello World'
        sh 'echo Building'
        sleep 10
      }
    }
    stage('Test') {
      steps {
        input "Does the staging environment look ok?"
      }
    }
    stage('Deploy') {
      steps {
        sh 'echo Deploying'
      }
    }
    stage('Post Deploy') {
      steps {
        echo 'Done'
      }
    }
  }
}

<<<<<<< HEAD
pipeline {  

  agent any

  agent { 
    docker { 
      image 'node:6-alpine' 
      args '-p 3000:3000'
    }
  }

  environment {
    ENV_VAR = 'value'
  }

  stages { 

    stage('Build') { 
=======
pipeline {
  agent any
  stages {
    stage('Build') {
>>>>>>> 6039103728a3699271e338f9ba6c6a9f6969db5a
      steps {
        echo 'Hello World'
        sh 'echo Building'
        sleep 10
      }
    }
<<<<<<< HEAD

    stage('Sanity check') {
=======
    stage('Test') {
>>>>>>> 6039103728a3699271e338f9ba6c6a9f6969db5a
      steps {
        input "Does the staging environment look ok?"
      }
    }
<<<<<<< HEAD
  }

  post {
    always {}
    success {
      slackSend channel: '#ops-room',
      color: 'good',
      message: "The pipeline ${currentBuild.fullDisplayName} completed successfully."
    }
    unstable {}
    failure {
      mail to: 'team@example.com',
      subject: "Failed Pipeline: ${currentBuild.fullDisplayName}",
      body: "Something is wrong with ${env.BUILD_URL}"
    }
    changed {}
=======
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
>>>>>>> 6039103728a3699271e338f9ba6c6a9f6969db5a
  }
}
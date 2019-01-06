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
      steps {
        echo 'Hello World'
        sh 'echo Building'
        sleep 10
      }
    }

    stage('Sanity check') {
      steps {
        input "Does the staging environment look ok?"
      }
    }
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
  }
}

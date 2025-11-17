pipeline {
  agent any
  environment {
    MY_GLOBAL_VARIABLE = 'value'
  }
  stages {
    stage ("Example") {
      steps {
        echo "Global value: ${env.MY_GLOBAL_VARIABLE}"
      }
    }
    stage("Build") {
      steps {
        echo "Building app..."
      }
    }
    stage("Test") {
      steps {
        echo "Testing app..."
      }
    }
    stage("Deploy") {
      steps {
        echo "Deploying app..."
        sh "./deploy staging"
      }
    }
    stage("Production") {
      steps {
        echo :Producting app..."
        sh "./deploy production"
      }
    }
  }
}

post {
  always {
    DeleteDir()
  }
  failure {
    echo "Failed"
    mail to: "zilberhleitmark@mail.ru"
    subject: "${env.JOB_NAME} - Build # ${env.BUILD_NUMBER} failed"
    body: "For context about pipeline fail check console output on address ${env.BUILD_URL}"
  }
}

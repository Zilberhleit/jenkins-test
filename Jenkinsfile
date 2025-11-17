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
      }
    }
  }
}

post {
  always {
    DeleteDir()
  }
}

pipeline {
  agent any
  stages {
    stage(‘Error’) {
      steps {
        error “failure test. It’s work”
      }
    }
    stage(‘ItNotWork’) {
      steps {
        echo “is not pass here”
      }
   }
  }
  post {
    success {
      office365ConnectorSend message: "Update Service in "
    }
    failure {
        office365ConnectorSend message: "Delete Service in"
    }
  }
}

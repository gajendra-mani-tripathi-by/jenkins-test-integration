pipeline {
  agent any
  stages {
    stage("Error") {
       echo "failure test. It’s work"
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

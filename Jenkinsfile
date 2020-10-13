pipeline {
    agent any 
    stages {
        stage('print_hello') {
            steps {
                echo 'Hello world!' 
            }
        }
    }
  post {
    success {
      office365ConnectorSend message: "Update Service in", status: "Success", webhookUrl:"https://outlook.office.com/webhook/e5d5d645-ddf2-43a9-bd9a-236a1487556d@2ac36cee-0617-4ac0-bebf-e1ce5dfab86c/JenkinsCI/320d5130b2d64b298da0c466b46d6f01/5c81ff39-6baf-49e1-a3d7-9a0505c4a745", color:"05b222"
    }
    failure {
        office365ConnectorSend message: "Delete Service in"
      office365ConnectorSend message: "Delete Service in", status: "Failed", webhookUrl:"https://outlook.office.com/webhook/e5d5d645-ddf2-43a9-bd9a-236a1487556d@2ac36cee-0617-4ac0-bebf-e1ce5dfab86c/JenkinsCI/320d5130b2d64b298da0c466b46d6f01/5c81ff39-6baf-49e1-a3d7-9a0505c4a745", color: "d00000"
    }
  }
}

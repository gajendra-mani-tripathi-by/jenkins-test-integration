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
    always {
      script {
        slackNotify {
          slackNotifyChannel='#project'
        }
     }
    }
  }
}

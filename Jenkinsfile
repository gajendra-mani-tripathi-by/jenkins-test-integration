pipeline {
    agent any 
    stages {
        stage('print_hello') {
            steps {
                echo 'Hello world!'
                exit(1)
            }
        }
    }
  post {
    always {
      script {
        slackNotify {
          slackNotifyChannel='@Gajendra Mani Tripathi '
        }
     }
    }
  }
}

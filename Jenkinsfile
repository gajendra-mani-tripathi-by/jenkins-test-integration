pipeline {
    agent any 
    stages {
        stage('print_hello') {
            steps {
                echo 'Hello world!'
            }
        }
    }
   post{
        success{
    	    script{ currentBuild.result = 'SUCCESS' }
        }
        cleanup{
            script{
                slackNotify{
                    slackNotifyChannel="#project"
                    slackNotifyBranches=[]
                }
            }
        }
    }
}

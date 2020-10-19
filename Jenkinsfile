def hookurl="https://outlook.office.com/webhook/e5d5d645-ddf2-43a9-bd9a-236a1487556d@2ac36cee-0617-4ac0-bebf-e1ce5dfab86c/JenkinsCI/3caba048188d4e0c9aad0c27d5587b0f/5c81ff39-6baf-49e1-a3d7-9a0505c4a745"
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
       success {
           script{
               msteamNotify{
                   msteamNotifyWebhook="${hookurl}"
                   msteamNotifyBranches=[]
               }
            }
        }
    }
}

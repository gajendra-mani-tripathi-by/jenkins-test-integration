import com.mycompany.TestSummary
url="https://outlook.office.com/webhook/e5d5d645-ddf2-43a9-bd9a-236a1487556d@2ac36cee-0617-4ac0-bebf-e1ce5dfab86c/JenkinsCI/0d4a42e63cca4b91835daa736e9e35f3/5c81ff39-6baf-49e1-a3d7-9a0505c4a745"
pipeline {
    agent any
    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
    }
    post {
        always {
            script {
                def newobj = new TestSummary(script:this)
                label = newobj.getLabel()
                testres = newobj.getTestSummary2()
                coverageres = newobj.getCoverageSummary()
                cause = newobj.getBuildCauseMessages()
                changes = newobj.getChanges()
                message = "${label} - [${BUILD_URL}](${BUILD_URL}) \n\n${testres}\n\n${coverageres}\n\n${cause}\n\n${changes}"
            }
        }
        changed {
            sh "curl -H \'Content-Type: application/json\' -d \'{\"@type\": \"MessageCard\", \"title\": \"Jenkins Build Status ==> ${JOB_NAME}\", \"text\": \"${message}\" }\' ${url}"
        }
    }
}

pipeline {
    agent any
    stages {
        stage('Call SQS queue') {
            steps {
                script {
                    sh '''aws sqs send-message --region ap-southeast-1 --endpoint-url https://sqs.ap-southeast-1.amazonaws.com/ --queue-url https://sqs.ap-southeast-1.amazonaws.com/006195751431/UAT-pitsop-email-owner --message-body "{\"type\":\"NEW_PITSTOP_NOTIFY\",\"data\":{\"emailTo\":[\"$email\"],\"userName\":\"$UserName\",\"orgName\":\"$OrgName\",\"pitstopName\":\"$PitstopName\"}}""'''    
                }
            }
        }
    }
}

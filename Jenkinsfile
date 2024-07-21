pipeline{
    agent any

    stages{
        stage('zip the file'){
            steps{
                sh 'zip ansible-${BUILD_ID}.zip * --exclude Jenkinsfile'
            }
        }
        stage ('upload artifacts to jfrog'){
            steps{
                sh 'curl -uadmin:AP5dvKeFbyogQNVFuetP7BAZSSs -T \
                 ansible-${BUILD_ID}.zip\
                  "http://ec2-44-211-43-148.compute-1.amazonaws.com:8081/artifactory/ansible1/ansible-${BUILD_ID}.zip"'
            }
        }
    }
}
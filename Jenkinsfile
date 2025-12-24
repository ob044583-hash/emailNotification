pipeline {
    agent any
 
    stages {
        stage('Build') {
            steps {
                echo "Building application..."
            }
        }
    }
 
    post {
        success {
            emailext(
                to: 'shaik.jawharulla@enhancesys.com,omprakash.biradar@enhancesys.com',
                subject: "SUCCESS: ${JOB_NAME} #${BUILD_NUMBER}",
                body: "Build succeeded.\n\nBuild URL: ${BUILD_URL}"
            )
        }
 
        failure {
            emailext(
                to: 'shaik.jawharulla@enhancesys.com,omprakash.biradar@enhancesys.com',
                subject: "FAILURE: ${JOB_NAME} #${BUILD_NUMBER}",
                body: "Build failed.\n\nCheck logs: ${BUILD_URL}console"
            )
        }
    }
}

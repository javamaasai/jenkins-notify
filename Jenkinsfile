pipeline {
    agent any
     
    stages {
        stage('Ok') {
            steps {
                echo "Ok"
            }
        }
    }
    post {
        always {
            emailext mimeType: 'text/html',
            subject: "Build [#${env.BUILD_NUMBER}] Info",
            to: 'isaac.khaguli@turnkeyafrica.com',
            body: readFile("build-notify/notify.html")
        }
    }
}
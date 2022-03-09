def success_build_status = '''<span style="color: #19c106">Succeded</span'''
def body_build_status = readFile("build-notify/notify.html")

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
            body: """
            ${body_build_status}
            """
        }
    }
}
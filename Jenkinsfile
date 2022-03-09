def success_build_status = '''<span style="color: #19c106">Succeded</span'''


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
            def body_build_status = readFile("build-notify/notify.html")
            emailext mimeType: 'text/html',
            subject: "Build [#${env.BUILD_NUMBER}] Info",
            to: 'isaac.khaguli@turnkeyafrica.com',
            body: """
            ${body_build_status}
            """
        }
    }
}
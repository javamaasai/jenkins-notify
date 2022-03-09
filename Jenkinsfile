def success_build_status = '''<span style="color: #19c106">Succeded</span'''
def engine = new groovy.text.SimpleTemplateEngine()
def templatex = engine.createTemplate(text).make(binding)
def binding = ["firstname":"Sam", "lastname":"Pullara", "city":"San Francisco", "month":"December", "signed":"Groovy-Dev"]
def template = engine.createTemplate(readFile("build-notify/notify.txt")).make(binding)

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
            body: templatex.toString()
        }
    }
}
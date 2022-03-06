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

                <div id="content">

                <h1>CI The report </h1>

                <div id="sum2">

                    <h2>Jenkins  Running results </h2>

                    <ul>

                    <li>jenkins The results of the implementation of  : <a>jenkins  Successful implementation </a></li>

                    <li>jenkins Of Job name  : <a id="url_1">${env.JOB_NAME} [${env.BUILD_NUMBER}]</a></li>

                    <li>jenkins Of URL : <a href='${env.BUILD_URL}'>${env.BUILD_URL}</a></li>

                    <li>jenkins Project name  : <a>${env.JOB_NAME}</a></li>

                    <li>Job URL : <a href='${env.BUILD_URL}'>${env.BUILD_URL}</a></li>

                    <li> The build log ：<a href="${BUILD_URL}console">${BUILD_URL}console</a></li>

                    </ul>

                </div>

                <div id="sum0">

                <h2>GIT  Information </h2>

                <ul>

                    <li>GIT Address of the project  : <a>${git_url}</a></li>

                    <li>GIT The name of the current branch of the project  : ${ref}</li>

                    <li>GIT Last submitted commitID : ${commits_id}</li>

                </ul>

                </div>

                </div>

                """,

            charset: 'utf-8'
        }
    }
}
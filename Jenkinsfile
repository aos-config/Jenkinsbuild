pipeline {
    agent any
    environment {
        PR_LIST = credentials('PR_LIST')
        TICKET_NAME = credentials('TICKET_NAME')
        GITHUB_TOKEN = credentials('GITHUB_TOKEN')
        RELEASE_NAME = credentials('RELEASE_NAME')
    }
    stages {
        stage('Run Docker Container') {
            steps {
                script {
                    sh """
                    docker pull arijitanand/mytestimage:99999
                    docker run --rm \
                        -e PR_LIST=\$PR_LIST \
                        -e TICKET_NAME=\$TICKET_NAME \
                        -e GITHUB_TOKEN=\$GITHUB_TOKEN \
                        -e RELEASE_NAME=\$RELEASE_NAME \
                        arijitanand/mytestimage:99999
                    """
                }
            }
        }
    }
}


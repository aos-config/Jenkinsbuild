pipeline {
    agent any
    parameters {
        string(name: 'PR_LIST', description: 'Comma-separated PR links')
        string(name: 'TICKET_NAME', description: 'Ticket link')
        password(name: 'GITHUB_TOKEN', description: 'GitHub Token')
        string(name: 'RELEASE_NAME', description: 'Release name in format 2025-R03')
    }
    stages {
        stage('Run Docker Container') {
            steps {
                script {
                    sh """
                    docker pull arijitanand/mytestimage:777
                    docker run --rm \
                        -e PR_LIST=\$PR_LIST \
                        -e TICKET_NAME=\$TICKET_NAME \
                        -e GITHUB_TOKEN=\$GITHUB_TOKEN \
                        -e RELEASE_NAME=\$RELEASE_NAME \
                        arijitanand/mytestimage:4200
                    """
                }
            }
        }
    }
}


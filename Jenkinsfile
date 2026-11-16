pipeline {
    agent any
    stages {
        stage ('build') {
            steps {
                docker build -t tooplate .
            }
        }
        stage ('deploy') {
            docker rm -f tooplate-site || true
            docker run -d --name tooplate-site -p 8081:80 tooplate
        }
    }
}

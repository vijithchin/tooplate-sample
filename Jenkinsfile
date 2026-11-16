pipeline {
    agent any
    stages {
	stage ('checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/vijithchin/tooplate-sample.git'
            }
        }
        stage ('build') {
            steps {
                sh 'docker build -t tooplate .'
            }
        }
        stage ('deploy') {
            sh '''
		docker rm -f tooplate-site || true
            	docker run -d --name tooplate-site -p 8081:80 tooplate
	'''
        }
    }
}

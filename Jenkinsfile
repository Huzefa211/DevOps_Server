pipeline {
    agent any

    stages {
        stage('Git Clone') {
            steps {
                git branch: 'main',
                url: 'https://github.com/Huzefa211/DevOps_Server.git'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t test2 .'
            }
        }

        stage('Docker Run') {
            steps {
                sh '''
                docker rm -f testc1 || true
                docker run -d -p 8080:80 --name testc1 test2
                '''
            }
        }
    }
}

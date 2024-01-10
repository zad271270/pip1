pipeline {
    agent any

    stages {
        stage('checkout & build') {
            steps {
                sh 'printenv'
                sh 'docker build -t dazarate1970/web -f Dockerfile .'
            }
        }
        
        stage('push to docker hub') {
            
            steps {
                withCredentials([string(credentialsId: 'DOCKER_USER', variable: 'DOCKER_USER'), string(credentialsId: 'DOCKER_PASSWD', variable: 'DOCKER_PASSWD')]) {
                sh 'docker login -u $DOCKER_USER -p $DOCKER_PASSWD'
                sh 'docker push dazarate1970/web'
                }
            }
        }
    }
}

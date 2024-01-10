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
                sh 'docker login -u dazarate1970 -p Toto2712!'
                sh 'docker push dazarate1970/web'
            }
        }
    }
}

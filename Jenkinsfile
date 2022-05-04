pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'sudo -S npm install'
                sh 'sudo -S npm run build'
            }
        }
        stage('Deploy') {
            steps {
                sh 'sudo -S rm -rf /var/www/jenkins-react-app'
                sh "sudo -S  cp -r ${WORKSPACE}/build/ /var/www/jenkins-react-app/"
            }
        }
    }
}

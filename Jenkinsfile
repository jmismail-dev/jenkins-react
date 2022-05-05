/* groovylint-disable-next-line CompileStatic */
pipeline {
    agent any
    tools { nodejs 'nodejs' }
    stages {
        stage('Test npm') {
            steps {
                sh '''
          npm --version
        '''
            }
        }
        stage('Build') {
            steps {
                sh 'sudo npm install'
                sh 'sudo npm run build'
            }
        }
        stage('Deploy') {
            steps {
                sh 'sudo rm -rf /var/www/jenkins-react-app'
                sh "sudo cp -r ${WORKSPACE}/build/ /var/www/jenkins-react-app/"
            }
        }
    }
}

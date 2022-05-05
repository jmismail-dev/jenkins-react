/* groovylint-disable-next-line CompileStatic */
pipeline {
    agent any
    tools { nodejs 'NodeJs' }
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
                sh 'npm install'
                sh 'npm run build'
            }
        }
        stage('Deploy') {
            steps {
                sh 'sudo rm -rf /var/www/jenkins-react-app'
                sh "cd  ${WORKSPACE} && mkdir build"
                sh "sudo cp -r ${WORKSPACE}/build/ /var/www/jenkins-react-app/"
                sh 'cd /var/www/jenkins-react-app/ && ls'
            }
        }
    }
}

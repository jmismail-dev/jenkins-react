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
                sh 'sudo -S  rm -rf /var/www/jenkins-react-app'
                // sh "cd  ${WORKSPACE} && mkdir build"
                sh "cd ${WORKSPACE}/dist && ls"
                sh "sudo -S cp -r ${WORKSPACE}/dist/ /var/www/jenkins-react-app/"
                // sh 'pm2 delete 0'
                // sh 'cd /var/www && mkdir jmismail'
            // sh 'cd /var/www/jenkins-react-app/ && ls'
            }
        }
    }
}

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
                // sh "cd  ${WORKSPACE} && mkdir build"
                sh "cd ${WORKSPACE} && ls"
                sh "sudo cp -r ${WORKSPACE}/dist/ /var/www/jenkins-react-app/"
            // sh 'mkdir /var/www/jmismail'
            // sh 'cd /var/www/jenkins-react-app/ && ls'
            }
        }
    }
}

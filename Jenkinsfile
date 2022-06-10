pipeline{
    agent{ label 'JDK_11'}
    stages{
        stage('Source Code'){
            steps {
                git branch:'main', url: 'https://github.com/manasbishoyi/Nodejs_declarative.git'
            }
        }
        stage('Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }
        stage('Archiving the project') {
            steps {
                sh script: 'npm pack'
            }
        }
        stage('Test results') {
            steps {
                sh 'npm test'
            }
        }
        stage('Sonar Analysis') {
            steps {
                sh 'npm run sonar'
            }
        }

    }
}
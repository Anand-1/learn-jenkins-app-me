pipeline {
    agent any
    stages {
        stage('With Docker') {
            agent{
                docker{
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
              sh '''
              ls -la
              node --version
              npm --version
              npm ci
              npm run build
              ls -la
              '''
            }
        }
        stage('Test'){
            steps{
                sh 'test -f build/index.html'
            }
        }
         stage('Deploy to Netlify') {
            agent{
                docker{
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
             steps{
                sh '''
                npm install netlify-cli
                node_modules/.bin/netlify --version
                '''
            }
        }
    }
}
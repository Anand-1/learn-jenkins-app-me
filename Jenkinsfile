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
              echo "With docker
              ls -la
              node --version
              npm --version
              npm ci
              npm run build
              ls -la
              '''
            }
        }
    }
}
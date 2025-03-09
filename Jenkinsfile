pipeline {
    agent any
    stages {
        stage('With Docker') {
            agent{
                docker{
                    image 'node:18-alpine'
                }
            }
            steps {
              sh 'echo "With docker"'
            }
        }
    }
}
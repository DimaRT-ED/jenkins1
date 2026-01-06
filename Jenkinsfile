pipeline {
    agent any

    stages {
        stage('1-Build') {
            steps {
                sh "ls -la"
                sh "pwd"
                sh '''
                  echo "Start of Stage Build"  >> log.log
                  echo "Building......."
                  echo "End of Stage Build" >> log.log
                '''
            }
        }
        stage('2-Test') {
            steps {
                sh '''
                  echo "Start of Stage Test" >> log.log
                  echo "Testing......."
                  echo "End of Stage Build" >> log.log
                '''
            }
        }
        stage('3-Deploy') {
            steps {
                sh '''
                  echo "Start of Stage Deploy" >> log.log
                  echo "Deploying......."
                  echo "End of Stage Build" >> log.log

                  ls -la
                  cat README.md
                  cat log.log
                '''
            }
        }
    }
}

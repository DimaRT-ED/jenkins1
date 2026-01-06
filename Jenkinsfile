pipeline {
    agent any
    environment {
        OWNER = "Dima"
        PROJECT = "Jenkins course"
    }

    stages {
        stage('1-Build') {
            steps {
                sh "ls -la"
                sh "pwd"
                sh '''
                  echo " this is project ${PROJECT} and his owner is ${OWNER}"
                  echo "Job $JOB_NAME Start of Stage Build"  >> log.log
                  echo "Building......."
                  echo "End of Stage Build" >> log.log
                '''
            }
        }
        stage('2-Test') {
            environment{
                PROJECT = "Stage 2 : Test"
            }
            steps {
                sh '''
                  echo " this is project $PROJECT and his owner is $OWNER"
                  echo "Start of Stage Test" >> log.log
                  echo "Testing......."
                  echo "End of Stage Build" >> log.log
                '''
            }
        }
        stage('3-Deploy') {
            steps {
                sh '''
                  echo " this is project $PROJECT and his owner is $OWNER"
                  echo "Start of Stage Deploy" >> log.log
                  echo "Deploying......."
                  echo "Job $JOB_NAME End of Stage Build" >> log.log

                  ls -la
                  cat README.md
                  cat log.log
                '''
            }
        }
        stage("try & retry"){
            steps{
                retry(3) { 
			        sh 'echo "in retry"'
		        }
		        timeout(time: 7, unit: 'SECONDS') { 
			        sh 'sleep 5' 
                    sh 'echo HELLO'
		        } 
            }
        }
    }
}

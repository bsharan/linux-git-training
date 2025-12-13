pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Code already checked out by Jenkins'
            }
        }

        stage('Verify Files') {
            steps {
                sh '''
                  echo "Listing repository files:"
                  ls -la
                '''
            }
        }

        stage('Git History') {
            steps {
                sh '''
                  echo "Recent commits:"
                  git log --oneline -3
                '''
            }
        }
    }
}

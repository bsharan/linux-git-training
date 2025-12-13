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
          echo "Checking README standardization..."
          if [ -f readme.md ] && [ -f README.md ]; then
            echo "ERROR: Both readme.md and README.md exist"
            exit 1
          fi
          echo "README naming is clean"
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
stage('Docker Build') {
    steps {
        sh '''
          docker build -t linux-git-training:ci .
        '''
    }
}
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
                  echo "Checking README standardization..."
                  if [ -f readme.md ]; then
                    echo "ERROR: readme.md should not exist"
                    exit 1
                  fi
                  echo "README naming is clean"
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

        stage('Docker Build') {
            steps {
                sh '''
                  docker build -t linux-git-training:ci .
                '''
            }
        }
    }
}

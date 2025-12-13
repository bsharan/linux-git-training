pipeline {
    agent any

    stages {
        stage('Verify Files') {
            steps {
                sh 'ls -la'
            }
        }

        stage('Check README') {
            steps {
                sh '''
                  if [ -f readme.md ]; then
                    echo "ERROR: readme.md exists"
                    exit 1
                  fi
                  echo "README naming OK"
                '''
            }
        }
    }
}

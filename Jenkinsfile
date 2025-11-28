pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        echo '🔄 Checking out code...'
        checkout scm
      }
    }
    stage('Setup Python Environment') {
      steps {
        echo '🐍 Creating virtual environment and installing dependencies...'
        sh '''
          python3 -m venv venv
          . venv/bin/activate
          pip install -r requirements.txt
        '''
      }
    }
    stage('Run App') {
      steps {
        echo '🚀 Running Python app...'
        sh '''
          . venv/bin/activate
          python app.py
        '''
      }
    }
  }
}


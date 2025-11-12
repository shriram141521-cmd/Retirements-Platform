pipeline {
  agent any

  environment {
    GIT_CREDENTIALS = 'shriram141521'
  }

  stages {
    stage('Clone') {
      steps {
        git credentialsId: "${env.GIT_CREDENTIALS}", url: 'https://github.com/shriram141521-cmd/Retirements-Platform.git'
      }
    }

    stage('Install Dependencies') {
      steps {
        sh 'npm install'
      }
    }

    stage('Run Tests') {
      steps {
        sh 'npm test'
      }
    }

    stage('Build Package') {
      steps {
        sh 'npm run build'
      }
    }

    stage('Archive Artifacts') {
      steps {
        archiveArtifacts artifacts: 'dist/**', fingerprint: true
      }
    }
  }
}

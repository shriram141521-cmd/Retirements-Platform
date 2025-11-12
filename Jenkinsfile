pipeline {
    agent any

    triggers {
        githubPush()
    }

    stages {
        stage('Checkout') {
            steps {
                // Clone the source code
                git branch: 'main', url: 'https://github.com/shriram141521-cmd/Retirements-Platform.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the project...'
                sh './gradlew build' // or mvn clean install, npm install, etc.
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh './gradlew test' // or npm test, etc.
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                // Add deployment script here
            }
        }
    }

    post {
        success {
            echo 'Build and test succeeded!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}

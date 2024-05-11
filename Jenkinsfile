pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from Git repository
                checkout([$class: 'GitSCM',
                          branches: [[name: '*/main']],
                          userRemoteConfigs: [[url: 'https://github.com/2023MT93353/devopsassignment2']]])
            }
        }

        stage('Compile') {
            steps {
                bat 'mvn clean compile'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn install'
            }
        }
    }

    post {
        success {
            echo 'Build Success'
        }
        failure {
            // If build fails, send a notification or take other actions
            echo 'Build failed! Please check the build logs.'
        }
        always {
            // Clean up workspace after the build is complete
            cleanWs()
        }
    }
}

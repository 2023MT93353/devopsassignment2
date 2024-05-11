pipeline {
    agent any

    stages {

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

            echo 'Build failed! Please check the build logs.'
        }
        always {
            // Clean up workspace after the build is complete
            cleanWs()
        }
    }
}

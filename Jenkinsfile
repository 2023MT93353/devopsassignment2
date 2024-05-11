pipeline {
    agent any

    stages {
        //stage('Checkout') {
          //  steps {
                // Checkout code from GitHub
            //    git credentialsId: 'your-github-credentials', url: 'https://github.com/your-org/your-repo.git'
            //}
        //}

        stage('Build') {
            steps {
                // Run Maven build
                sh 'mvn clean install'
            }
        }
    }

    post {
        success {
            // If build succeeds, archive artifacts (e.g., JAR files)
            archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
        }
        failure {
            // If build fails, send email notification to developers
            //emailext attachLog: true, recipients: 'developers@example.com', subject: 'Build Failed', body: 'The build failed. Please check Jenkins for details.'
        }
    }
}

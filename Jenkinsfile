pipeline {
    agent any

    stages {
            stage('Compile') {
                steps {
                    bat 'mvn clean compile'
                }
            }
            stage('build') {
                steps {
                    bat 'mvn install'
                }
            }
        post {
            success {
                // If build succeeds, archive the build artifacts
                archiveArtifacts artifacts: '**/target/*.jar', allowEmptyArchive: true
            }
            failure {
                // If build fails, send a notification or take other actions
                echo 'Build failed! Please check the build logs.'
            }
        }
    }
}

post {
    always {
// Clean up workspace after the build is complete

        cleanWs()
    }
}


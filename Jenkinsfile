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


}

pipeline {
    agent any

    stages {
            stage('Checkout') {
                steps {
                    // This stage will checkout the code from the repository automatically
                    checkout scm
                }
            }

            stage('Compile and Build') {
                steps {
                    // Run Maven compile and build
                    sh 'mvn clean compile package'
                }
            }
        }


}

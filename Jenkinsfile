pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    sh "g++ Jenkinfile.cpp -o PES1UG21CS339-1"  // Compile with desired flags
                }
            }
        }

        stage('Test') {
            steps {
                // **Intentional error:** Introduce an undefined variable
                sh "undefined_variable ./PES1UG21CS339-1"  // Run the compiled executable (error occurs here)
            }
        }

        stage('Deploy') {
            steps {
                // Add your deployment steps here
                echo "Deploying the application..."
            }
        }
    }

    post {
        always {
            // Cleanup actions, always executed
            echo "Cleaning up workspace..."
        }
        success {
            echo "Pipeline successful!"
        }
        failure {
            echo "Pipeline failed!"  // This will be printed upon failure
        }
    }
}

pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                sh '''
                echo "Building Java project..."
                ls
                cd "Password Protection"
                mkdir -p build
                javac -d build src/*.java
                echo "Build successful"
                '''
            }
        }

        stage('Test') {
            steps {
                sh '''
                echo "Running tests..."
                cd "Password Protection"
                echo "JUnit tests simulated"
                '''
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                echo "Packaging application..."
                cd "Password Protection"
                jar cf FileEncrypter.jar -C build .
                echo "Artifact created"
                '''
            }
        }
    }

    post {
        success {
            echo "Pipeline executed successfully!"
        }

        failure {
            echo "Pipeline failed!"
        }
    }
}

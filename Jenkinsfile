pipeline {
    agent any

    environment {
        JAVA_HOME = 'C:\Program Files\Java\jdk-23'  // Path to Java on Ubuntu
        PATH = "${JAVA_HOME}/bin:${env.PATH}"
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from your Git repository
                git branch: 'main', url: 'https://github.com/adityavarma0505/sample.git'  // Replace with your Git repo URL
            }
        }

        stage('Build') {
            steps {
                // Compile the Java code using javac
                sh 'javac HelloWorld.java'
            }
        }

        stage('Run') {
            steps {
                // Run the Java program using java
                sh 'java HelloWorld'
            }
        }
    }

    post {
        always {
            // Clean up or run any post-build actions
            echo 'Pipeline finished.'
        }
    }
}

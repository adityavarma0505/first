pipeline {
    agent any

    environment {
        JAVA_HOME = '/usr/lib/jvm/java-23-openjdk'  // Change this if Java is installed elsewhere
        PATH = "${JAVA_HOME}/bin:${env.PATH}"
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/adityavarma0505/sample.git'
            }
        }

        stage('Build') {
            steps {
                script {
                    def javaFiles = sh(script: "find . -name '*.java'", returnStdout: true).trim()
                    if (javaFiles) {
                        sh 'javac *.java'
                    } else {
                        error "No Java files found to compile."
                    }
                }
            }
        }

        stage('Run') {
            steps {
                sh 'java HelloWorld'  // Ensure the class contains a valid `main` method
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished.'
        }
    }
}


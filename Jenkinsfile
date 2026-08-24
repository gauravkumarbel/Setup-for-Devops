pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Yahan aapka Git repo aayega
                git branch: 'main', url: 'https://github.com/gauravkumarbel/learning.git'
            }
        }

        stage('Build') {
            steps {
                // Yahan apna build command daalo — jo language ho usi ka
                sh  docker build -t my-web-app:1.0
                
                // Example - agar Node.js project hai:
                // sh docker run -d -p 8080:80 --name my-web-server nginx

              
            }
        }

        stage('Test') {
            steps {
                sh 'echo "Yahan apna test command likho"'
            }
        }

        stage('Deploy') {
            steps {
                sh 'echo "Yahan apna deploy command likho"'
            }
        }
    }

    post {
        success {
            echo 'Pipeline successfully complete hua!'
        }
        failure {
            echo 'Pipeline fail ho gaya, logs check karo.'
        }
    }
}

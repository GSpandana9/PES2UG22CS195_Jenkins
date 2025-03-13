pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/GSpandana9/PES2UG22CS195_Jenkins'
            }
        }

        stage('Build') {
            steps {
                sh 'g++ 195.cpp -o PES2UG22CS195-1'
            }
        }

        stage('Test') {
            steps {
                sh './PES2UG22CS195-1'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                git config --global user.email "spandanag31@gmail.com"
                git config --global user.name "GSpandana9"
                git add 195.cpp
                git commit -m "Added new working .cpp file"
                git push origin main
                '''
            }
        }
    }

    post {
        failure {
            echo "Pipeline failed"
        }
    }
}

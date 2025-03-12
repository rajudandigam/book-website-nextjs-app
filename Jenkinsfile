pipeline {
    agent any

    stages {
        stage('Cloning the Code') {
            steps {
                git branch:'main', url: "https://github.com/<Your-Github-username>/book-website-nextjs.git"
            }
        }
         stage('Building the Docker Image') {
            steps {
                sh '''
                docker build -t book-read-app:v1 .
                '''
            }
        }
         stage('Running the Container') {
            steps {
                sh 'docker run --name book-reader -d -p 3000:3000 book-read-app:v1'
            }
        }
         stage('Access the App') {
            steps {
                echo 'Your Application is running on PublicIPAddress of your instance followed by port 3000'
            }
        }
    }
}

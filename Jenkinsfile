pipeline {
    agent {label "manoj"}

    stages {
        stage('Code') {
            steps {
                echo 'cloning..'
                git url: "https://github.com/iamtanya28/django-notes-app.git", branch:"main"
            }
        }
        stage('Build') {
            steps {
                echo 'building..'
                sh "docker build -t notes-app:latest ."
            }
        }
        stage('Push to DockerHub') {
            steps {
                echo 'testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'deploying..'
                sh "docker run -d -p 8000:8000 notes-app:latest"
            }
        }
    }
}


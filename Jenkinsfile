pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    // Docker imajını build et
                    sh 'docker build -t my-angular-app .'

                    // Docker imajına tag ekle
                    sh 'docker tag my-angular-app akipsoyu/my-angular-app:v2'
                }
            }
        }

        stage('Push to Docker Hub') {
            steps {
                script {
                    // Docker Hub'a giriş yap (Şifre açık bir şekilde burada)
                    sh 'echo "123456789ba*" | docker login --username akipsoyu --password-stdin'

                    // Docker imajını push et
                    sh 'docker push akipsoyu/my-angular-app:v2'
                }
            }
        }
    }
}


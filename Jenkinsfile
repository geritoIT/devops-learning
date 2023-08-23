pipeline {
    agent {
        docker {
            image 'nginx' // Az alkalmazás futtatásához használt Docker image (pl. nginx)
        }
    }
    stages {
        stage('Checkout') {
            steps {
                // A kód letöltése a GitHub-ról
                checkout scm
            }
        }
        stage('Run App in Docker') {
            steps {
                // Itt beállíthatod a környezeti változókat, szükséges konfigurációkat
                // Majd indíthatod az alkalmazást a Docker konténerben
                sh 'docker run -d -p 8080:80 -v $(pwd):/usr/share/nginx/html nginx'
            }
        }
    }
}
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Mengambil kode sumber dari repository Git
                checkout scm
            }
        }

        stage('Build') {
            steps {
                // Menampilkan versi Python
                sh 'python -V'
            }
        }

        stage('Test') {
            steps {
                // Menjalankan skrip Python sederhana
                sh 'python -c "print(\'Hello, Jenkins!\')"'
            }
        }
    }
}

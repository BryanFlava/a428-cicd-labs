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
                // Menjalankan skrip Python
                sh 'python -V' // Menampilkan versi Python
            }
        }
        
        stage('Test') {
            steps {
                // Menjalankan skrip Python untuk pengujian
                sh 'python -c "print(\'Hello, Jenkins!\')"'
            }
        }
    }
}

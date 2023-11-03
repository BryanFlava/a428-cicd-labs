pipeline {
    agent {
        docker {
            image 'node:16-buster-slim'
            args '-p 3000:3000'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }
        // menambah stage Manual Approval
        stage('Manual Approval') { 
            steps {
                timeout(time: 7, unit: 'DAYS') {
                    input message: 'Apakah sudah siap untuk dilanjutkan? (Klik "Proceed" untuk melanjutkan)'
                }
            }
        }
        stage('Deploy') { 
            steps {
                sh './jenkins/scripts/deliver.sh'
                sh 'sleep 60'  // Menjeda eksekusi selama 1 menit
                sh './jenkins/scripts/kill.sh'
            }
        }
    }
}

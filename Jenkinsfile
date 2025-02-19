pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Ravikanth28/nexus.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                bat 'flutter pub get'
            }
        }
        stage('Analyze Code') {
            steps {
                bat 'flutter analyze'
            }
        }
        stage('Run Tests') {
            steps {
                bat 'flutter test'
            }
        }
        stage('Build APK') {
            steps {
                bat 'flutter build apk'
            }
        }
        stage('Archive APK') {
            steps {
                archiveArtifacts artifacts: 'build/app/outputs/flutter-apk/app-release.apk', fingerprint: true
            }
        }
    }
}

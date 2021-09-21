pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo "HELLOP"
                echo "BUILD USERR $BUILD_USER"
                sh './gradlew build'
            }
        }
        stage('Test') {
            steps {
                sh './gradlew check'
            }
        }
    }

    post {
        always {
            archiveArtifacts artifacts: 'build/libs/**/*.jar', fingerprint: true
            junit 'build/reports/**/*.xml'
        }
    }
}
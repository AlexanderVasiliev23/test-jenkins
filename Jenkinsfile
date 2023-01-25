pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                container ('postgres-billing') {
                    sh 'echo "Hi A"'
                }
            }
        }
    }
}
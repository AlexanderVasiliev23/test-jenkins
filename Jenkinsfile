pipeline {
    agent {
        label 'master'
    }
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
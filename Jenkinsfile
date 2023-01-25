pipeline {
    agent {
        kubernetes {
            defaultContainer 'jnlp'
            yaml """
apiVersion: v1
kind: Pod
metadata:
  name: my-pod-name
  labels:
    name: my-pod-name-label
spec:
  containers:
    - name: postgres-billing
      image: postgres:11.15
      ports:
        - containerPort: 5432
          protocol: TCP
      env:
        - name: POSTGRES_DB
          value: "billing"
        - name: POSTGRES_USER
          value: "admin"
        - name: POSTGRES_PASSWORD
          value: "df324XdCE"
        - name: JENKINS_URL
          value: http://jenkins.operations:8080
        - name: JENKINS_TUNNEL
          value: jenkins-agent.operations:50000
"""
        }
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
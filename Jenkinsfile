pipeline {
    agent {
        kubernetes {
            label "podlabel"
            yaml """
kind: Pod
metadata:
  name: jenkins-agent
spec:
  containers:
  - name: kaniko
    image: alpine:3.13.0
    imagePullPolicy: Always
    tty: true
  restartPolicy: Never
"""
        }
    }

    stages {
        stage('test') {
            steps {
                sh("ls -la")
            }
        }
    }

}

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
    image: alpine:latest
    imagePullPolicy: Always
    command:
    - /bin/cat
    tty: true
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

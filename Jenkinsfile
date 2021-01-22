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
    command: ["/bin/sh"]
    args: ["-c", "sleep 10 && echo Sleep expired > /dev/termination-log"]
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

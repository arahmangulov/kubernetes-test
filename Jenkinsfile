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
    image: gcr.io/kaniko-project/executor:debug
    imagePullPolicy: Always
    tty: true
    command: 
    - /busybox/cat
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

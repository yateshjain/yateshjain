pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Remote') {
            steps {
                script {
                    sh """ssh root@192.168.29.132 << EOF
		    echo "Host Name"
                    hostname
                    echo "DISK SIZE of /"
		    df -h /
                    echo "MEMORY"
                    free -m
                    exit
                    EOF"""
                }
            }
        }
    }
}

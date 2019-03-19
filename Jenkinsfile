pipeline {
    agent any
    stages {
        stage ('clone') {
            steps {
                sh """
                git clone git@github.com:konef/backups.git
                file=\$(find /var/lib/jenkins/jobs/ -name config.xml)
                echo \$file
                """
            }
        }
        stage ('clean') {
            steps {
                cleanWs()
            }
        }
    }
}

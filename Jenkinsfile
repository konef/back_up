pipeline {
    agent any
    stages {
        stage ('clone') {
            steps {
                git credentialsId: '12fde15b-88f7-44c3-a289-7aa18d573518', url: 'https://github.com/konef/backups'
            }
        }
        stage ('back up') {
            steps {
                sh """
                for x in /$(find /var/lib/jenkins/jobs/ -name config.xml)
                do
                echo /$x
                done
                """
            }
        }
    }
}

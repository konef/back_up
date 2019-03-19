pipeline {
    agent any
    stages {
        stage ('clean') {
            steps {
                cleanWs()
            }
        }
        stage ('var') {
            steps {
                sh """
                echo "WORKSPACE" :: $WORKSPACE
                """
            }
        }
        stage ('clone') {
            steps {
                sh """
                git clone git@github.com:konef/backups.git
                for x in \$(find /var/lib/jenkins/jobs/ -name config.xml)
                do
                config=\$(echo \$x | cut -c 23-)
                cd /var/lib/jenkins/jobs
                cp -rf --parents \$config  backups/
                done
                """
            }
        }
        
    }
}

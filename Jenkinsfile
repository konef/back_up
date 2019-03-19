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
                leng=\$(expr length "$JENKINS_HOME/jobs/")
                for x in \$(find $JENKINS_HOME/jobs/ -name config.xml)
                do
                config=\$(echo \$x | cut -c \$leng-)
                #cd /var/lib/jenkins/jobs
                #cp -rf --parents \$config  $WORKSPACE/backups/
                cp -rf --parents $JENKINS_HOME/jobs/\$config  $JENKINS_HOME/workspace/qwerty
                done
                """
            }
        }
        
    }
}

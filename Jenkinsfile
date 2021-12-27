pipeline {
    agent any
    stages {
        stage('Example Build') {
             
            steps {
                echo 'ZIP Codebase'
                sh 'zip -r build.zip .'
            }
        }
        stage('Example Test') {
            steps {
                echo 'SHOW Path'
                sh 'pwd'
            }
        }
	stage('copybuild on remote host') {
    	    steps {
	      	echo 'COPY FILE TO REMOTE HOST'
		sh 'scp -r build.zip kundan@server1:/tmp/'
		sh 'ssh kundan@server1 sudo unzip -o -d /var/www/html/ /tmp/build.zip'
	    }
	}
    }
}

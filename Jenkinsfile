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
	node {
	  def remote = [:]
	  remote.name = 'server1'
	  remote.host = 'server1'
	  remote.user = 'kundan'
	  remote.password = 'kundan'
	  remote.allowAnyHosts = true
	  stage('copybuild on remote host') {
    	      steps {
	       	echo 'COPY FILE TO REMOTE HOST'
		sshPut remote: remote, from: 'build.zip', into: '/var/www/html/'
		sshCommand remote: remote, command: "unzip -o -d /var/www/html/ /var/www/html/"
	      }
	  }
	}
    }
}

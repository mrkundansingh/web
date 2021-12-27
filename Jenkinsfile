pipeline {
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
    }
}

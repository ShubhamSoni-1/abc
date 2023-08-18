pipeline {
    agent any

	
    stages {
       
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build'
		 }
        }
	stage('Deploy') {
	steps {
        	sh 'echo "sudoers config:"'
        	sh 'cat /etc/sudoers'
        	sh 'echo "Executing command:"'
        	sh 'echo "sudo -S cp -r build/* /var/www/html"'
        	sh 'sudo -S cp -r build/* /var/www/html'
		}
	}
}

	post {
		always {
			cleanWs()
		}
	}
}

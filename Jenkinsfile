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
        	sh 'cp -r build/* /var/www/html/'
		sh 'sudo nginx -s reload'
		}
	}
}

	post {
		always {
			cleanWs()
		}
	}
}

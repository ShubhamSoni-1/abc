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
		sh 'npm start '
		sh ' cp -r build/* /usr/share/nginx/html'
		sh 'systemctl restart nginx'
		}
	}
}

	post {
		always {
			cleanWs()
		}
	}
}

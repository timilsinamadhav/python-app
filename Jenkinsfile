pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building Docker Image'
		sh "whoami"
		sh "docker build -t timilsinamadhav/python-app ."
            }
        }
        stage('Tag and Publish') {
            steps {
                echo 'Pushing to dockerhub..'
		sh "docker push timilsinamadhav/python-app"
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
	stage('Cleanup') {
            steps {
                echo 'Cleaning pushed images....'
		sh "docker rmi timilsinamadhav/python-app"
            }
        }
    }
}

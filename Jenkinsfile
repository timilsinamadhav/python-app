pipeline {
    environment {
        registry = "timilsinamadhav/python-app"
    {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building Docker Image'
		sh "whoami"
		sh "docker build -t $registry ."
            }
        }
        stage('Tag and Publish') {
            steps {
                echo 'Pushing to dockerhub..'
		sh "docker push $registry"
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
		sh "docker rmi $registry"
            }
        }
    }
}

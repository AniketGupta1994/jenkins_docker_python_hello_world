pipeline {
agent any
environment {
DOCKER_IMAGE = 'hello-world-python:latest' // Docker image
}
stages {
stage ('Checkout') {
steps {
git branch: "main', url:
'https://github.com/AniketGupta1994/jenkins_docker_python_hello_world.git'
}
}
stage('Docker Build'){
	steps{
		sript{
			if(fileExits('Dockerfile')){
			sh "docker build -t ${env.DOCKER_IMAGE} ."
							}
			else{
				error "Docker file not found"
				}
			}
		}
	}
stage ('Docker Run'){
steps {
sh "docker run --rm ${env.DOCKER_IMAGE}"
} } }

post{
success {
echo 'Success.'
}
failure {
echo 'Dcker build failed'
}
}
}

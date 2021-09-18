env.DOCKER_REGISTRY = 'miqbalnawawi'
env.DOCKER_IMAGE_NAME = 'nodejs'
node('master') {
    
    stage('HelloWorld') {
        echo 'Hello World'
    }
    stage('Git Pull from Github') {
       git branch: 'main',url: 'https://github.com/miqbalnawawi/NodeJS---Jenkins.git'
    }
    stage('Build Docker Image') {
        sh "docker build --build-arg APP_NAME=nodejs -t $DOCKER_REGISTRY/$DOCKER_IMAGE_NAME:${BUILD_NUMBER} ."   
    }
    stage('Running Container') {
        sh "docker run -it -d --name nodejs2 -p 9001:9005 $DOCKER_REGISTRY/$DOCKER_IMAGE_NAME:${BUILD_NUMBER}"
    }
    
    stage("Clean Workspace"){
     cleanWs() 
        
    }
}

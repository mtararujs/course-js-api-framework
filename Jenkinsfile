pipeline {
    agent any
    triggers{
        pollSCM('*/1 * * * *')
    }
    stages {
        stage('build-api-test-image') {
            steps {
                buildDockerImage()
            }
        }
    }
}

def buildDockerImage(){
    echo "Building of node application is starting.."
    sh "docker build -t mtararujs/api-tests ."

    echo "Pushing image to docker registry.."
    sh "docker push mtararujs/api-tests"
}
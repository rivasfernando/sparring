pipeline{
    agent {
        docker { 
            image 'maven:3.8.6-openjdk-8-slim'
            args '--env=DOCKER_HOST=tcp://host.docker.internal:2375 -v $HOME/.m2'
        }
    }

    stages{
        stage("Checkout"){
            steps{
                echo "Checkout..."
                checkout scm
            }
        }

        stage("Build"){
            steps{
                echo "Building..."
                sh "mvn clean"
                sh "mvn package"
                archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
            }
        }

        stage("Docker build"){
            steps{
                echo "Building Docker image..."
            }
        }

        stage("Docker deploy"){
            steps{
                echo "Deploying..."
            }
        }

    }
}
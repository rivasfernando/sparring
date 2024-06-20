pipeline{
    agent any

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
                sh(mvn clean)
                sh(mvn package)
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
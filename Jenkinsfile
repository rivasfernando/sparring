pipeline{
    agent any

    stages{
        stage("Checkout"){
            steps{
                echo "Checkout..."
            }
        }

        stage("Build"){
            steps{
                echo "Building..."
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
pipeline{
    agent any

    tools {
        jdk "openjdk8"
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
                sh "java -version"
                sh "mvn clean package"
                archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
            }
        }

        stage("Docker build"){
            steps{
                echo "Building Docker image..."
                script {
                    def customImage = docker.build("sparring-web:${env.BUILD_ID}", "sparring-web")
                    def customImage = docker.build("sparring-admin:${env.BUILD_ID}", "sparring-admin")
                    def customImage = docker.build("sparring-db:${env.BUILD_ID}", "sparring-db")
                }
            }
        }

        stage("Docker deploy"){
            steps{
                echo "Deploying..."
            }
        }

    }
}
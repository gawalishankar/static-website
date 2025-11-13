pipeline {
    agent any

    environment {
        DOCKERHUB_CREDENTIALS = credentials('dockerhub')
        IMAGE_NAME = "shiv201/static-web"
    }

    triggers {
        githubPush()
    }

    stages {

        stage('Checkout Code') {
            steps {
                echo "📥 Cloning repository from GitHub..."
                git branch: 'main', url: 'https://github.com/gawalishankar/static-website.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                echo "🐳 Building Docker image..."
                sh '''
                    docker build -t $IMAGE_NAME:$BUILD_NUMBER .
                '''
            }
        }

        stage('Push to DockerHub') {
            steps {
                echo "📤 Pushing Docker image to DockerHub..."
                sh '''
                    echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin
                    docker push $IMAGE_NAME:$BUILD_NUMBER
                    docker tag $IMAGE_NAME:$BUILD_NUMBER $IMAGE_NAME:latest
                    docker push $IMAGE_NAME:latest
                '''
            }
        }

        stage('Deploy Container') {
            steps {
                echo "🚀 Deploying using Docker Compose..."
                sh '''
                    docker-compose down || true

                    docker-compose up -d
                '''
            }
        }
    }

    post {
        success {
            echo "✅ Deployment successful! App is live at port 8080."
        }
        failure {
            echo "❌ Build or deployment failed. Check logs for details."
        }
    }
}

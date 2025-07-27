pipeline {
    agent any

    environment {
        IMAGE_NAME = 'flaskapp-autodeployer:latest'
        CONTAINER_NAME = 'flaskapp'
        APP_PORT = '5000'
    }

    stages {

        stage('Clone Repository') {
            steps {
                echo "Cloning Git repository..."
                git branch: 'main', url: 'https://github.com/Harshwardhanjadhav0/DevOps-CICD-Flask-App-Project'
            }
        }

            stage('Installing pip command') {
            steps {
                echo "Installing Pip command..."
                sh 'sudo yum install python3-pip -y'
            }
        }

        stage('Install Python Dependencies') {
            steps {
                echo "Installing Python dependencies..."
                sh 'sudo pip3 install -r requirements.txt'
            }
        }

        stage('Run Unit Tests') {
            steps {
                echo "Running unit tests..."
                sh 'pytest'
            }
        }

        stage('Clean Old Docker Resources') {
            steps {
                echo "Stopping and removing any existing container..."
                sh """
                    sudo docker stop $CONTAINER_NAME || true
                    sudo docker rm $CONTAINER_NAME || true
                """
            }
        }

        stage('Build Docker Image') {
            steps {
                echo "Building Docker image..."
                sh "sudo docker build -t $IMAGE_NAME ."
            }
        }

        stage('Run Docker Container') {
            steps {
                echo "Running Docker container..."
                sh "sudo docker run -d -p $APP_PORT:$APP_PORT --name $CONTAINER_NAME $IMAGE_NAME"
            }
        }
    }

    post {
        success {
            echo 'Flask App Deployed Locally via Docker!'
        }
        failure {
            echo 'Build/Deployment Failed. Check Console Output.'
        }
    }
}


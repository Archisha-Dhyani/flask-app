pipeline{
  agent any
  environment{
    VENV = 'venv'
  }
  stages{
    stage('Checkout git'){
      steps{
        git branch: 'main', url: 'https://github.com/Archisha-Dhyani/flask-app.git'
      }
    }
    stage('image create'){
      steps{
        sh 'echo "Creating image"'
        sh 'docker build -t discount_image .'
      }
      }
    stage('create container'){
      steps{
        sh 'echo "Creating container"'
        sh 'docker run --name container_disc -p 5000:5000 discount_image'

      }
    }
    stage('push the image'){
      steps{
        sh 'echo "Pushing the image"'
        sh 'docker push discount_image'
      }
    }
  }
}

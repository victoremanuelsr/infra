pipeline{
  agent any
  environment {
    ARTIFACTORY_ACCESS_TOKEN = credentials('artifactory-access-token')
    DOCKER_ACCESS_TOKEN = credentials('docker-access-token')
    DOCKER_ACCESS_USERNAME = credentials('docker-access-username')
  }
  stages{
    stage('Download Artifactory'){
      steps{
        sh '/usr/local/bin/jf rt download --url https://victoremanuelsr.jfrog.io/artifactory/ --access-token ${ARTIFACTORY_ACCESS_TOKEN} /petstore/build/libs/*.war'
      }
    }
    stage('Build image docker and push for dockerhub'){
      steps{
        sh 'packer build --var docker_username=$DOCKER_ACCESS_USERNAME --var docker_password=$DOCKER_ACCESS_TOKEN --var docker_repository=victoremanuelsr/petstore packer.json'
      }
    }
  }
}
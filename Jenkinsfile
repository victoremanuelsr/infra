pipeline{
  agent any
  environment {
    ARTIFACTORY_ACCESS_TOKEN = credentials('artifactory-access-token')
    ARTIFACTORY_ACCESS_USERNAME = 'victoremanuelsr@outlook.com'
  }
  stages{
    stage('Download artifactory'){
      steps{
        sh 'curl -u ${ARTIFACTORY_ACCESS_USERNAME}:${ARTIFACTORY_ACCESS_TOKEN} -XGET https://victoremanuelsr.jfrog.io/artifactory/petstore/build/libs/PetStore.war --output PetStore.war'
      }
    }
  }
}
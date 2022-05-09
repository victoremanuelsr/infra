pipeline{
  agent any
  environment {
    ARTIFACTORY_ACCESS_TOKEN = credentials('artifactory-access-token')
    ARTIFACTORY_ACCESS_USERNAME = 'victoremanuelsr@outlook.com'
  }
  stages{
    stage('Download artifactory'){
      steps{
        sh 'curl -u victoremanuelsr@outlook.com:${ARTIFACTORY_ACCESS_TOKEN} -X GET "https://victoremanuelsr.jfrog.io/artifactory/petstore/build/libs/PetStore.war"'
        sh 'ls -la'
      }
    }
  }
}
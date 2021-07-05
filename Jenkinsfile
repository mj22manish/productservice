pipeline{
 environment {
imagename = "mjmanishdocker/productservice"
registryCredential = 'dockerpass'
dockerImage = ''
}
 agent any
 tools {
  maven 'maven3.6.3'
 }
 stages {
 stage('Build')
 {
  steps {
  script{
  sh "mvn clean install"
}
}
}
  stage('Build docker image') {
   steps{
    script{
     dockerImage = docker.build imagename
}
    }
   }
 stage('Deploy Image') {
 steps{
  script {
   docker login -u "mjmanishdocker" -p "Newcity@1" 
docker push mjmanishdocker/productservice:latest

  }
 }
 }
}
}

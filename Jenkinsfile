pipeline{
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
     docker build . --t mjmanishdocker\productservice:latest
     withCredentials([string(credentialsId: 'mjmanishdocker', variable: 'dockerpass')]) {
    docker login -u mjmanishdocker -p $dockerpass
      docker push mjmanishdocker\productservice:latest
}
    }
   }
  }
}
}

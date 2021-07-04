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
}
}

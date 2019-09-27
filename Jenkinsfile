pipeline {
  agent any
  tools{
    maven 'Maven';
    jdk 'JDK';
  }
  stages {
    stage('build') {
      steps {
        sh 'mvn clean install'
      }
      post {
        success {
          junit '**/target/surefire-reports/TEST-*.xml'
          archiveArtifacts 'target/*.jar'
        }
      }
    }
  }
}

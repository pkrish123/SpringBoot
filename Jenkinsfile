pipeline {
  agent any
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

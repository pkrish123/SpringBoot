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
    }
    stage('build and push docker image') {
      steps {
           // using google JIB plugin
           sh 'mvn compile com.google.cloud.tools:jib-maven-plugin:1.3.0:build -DsendCredentialsOverHttp=true'
      }
    }
  }
}

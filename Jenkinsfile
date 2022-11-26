pipeline {
  agent any
  tools {
    maven 'Maven' 
  }
  stages {
    stage ('Build') {
      steps {
//        checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'd817cfd8-3111-45df-8d1c-c1787ed73ed2', url: 'https://github.com/vishaldhiman86/hello-world-war.git']]])
        sh 'mvn clean package'
        echo "Hello Devops Engineers"

      }
    }
    stage ('Deploy') {
      steps {
        deploy adapters: [tomcat9(credentialsId: '533ab35c-caa3-4cfb-bf5c-a8ef3f12df52', path: '', url: 'http://52.7.85.74:8888/')], contextPath: 'hello-world-war-1.0.0', war: '**/*.war'
      }
    }
  }
}


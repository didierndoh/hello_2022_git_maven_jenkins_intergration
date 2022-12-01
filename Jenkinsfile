pipeline {
  agent any
  tools {
     maven 'M2_HOME'
  }
  environment {
<<<<<<< HEAD
     registry = "didierndoh/devops_pipeline_1"
=======
     registry = "ndohdidier/docker_pipeline"
>>>>>>> 41e6a013e293ef5f8471acef337cce4f2186815d
     registryCredential = 'DockerID'
  }
  stages {
    stage('Build'){
      steps {
       sh 'mvn clean'
       sh 'mvn install'
       sh 'mvn package'
     }
   }
    stage('test'){
      steps {
       echo "test step"
       sh 'mvn test'
     }
   }
    stage('deploy'){
      steps {
      script {
       docker.build registry + ":$BUILD_NUMBER"
      }
     }
   }
  }
}

pipeline {
  options {
    disableConcurrentBuilds()
  }
  agent {
    label "jenkins-jx-base"
  }
  environment {
    DEPLOY_NAMESPACE = "jx-staging"
  }
  stages {
    stage('Validate Environment') {
      steps {
        container('jx-base') {
          dir('pksjenkins') {

               sh 'jx step helm apply --name pksjenkins'
        
       
       }
        }

      }
    }
  }
}

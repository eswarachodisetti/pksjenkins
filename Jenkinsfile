pipeline {
  options {
    disableConcurrentBuilds()
  }
  agent {
    label "jenkins-maven"
  }
  environment {
    DEPLOY_NAMESPACE = "default"
  }
  stages {
    
    
     stage('Build') {
      steps {
        container('maven') {
          sh 'docker build -t docker-registry.jx.35.229.61.119.nip.io/poctest:7.0 .'
		      sh 'docker images'
	
        }

      }
    }
    
    
    	  
    stage('Push') {
		steps{
			script {
				container('maven') {
				
				//	sh 'mount -o remount,rw /home/jenkins/.docker'
				//	sh 'scp ${WORKSPACE}/config.json /home/jenkins/.docker/'
				//	sh 'docker push dhanapodigiri/poclistener:7.0'	
					sh 'docker push docker-registry.jx.35.229.61.119.nip.io/poctest:7.0'
				}
			
			}
		}
	}
	     
	
 /*   
    stage('Validate Environment') {
      steps {
        container('jx-base') {
          dir('pksjenkins') {

               sh 'jx step helm apply --name pksjenkins'
        
       
       }
        }

      }
    }
	  
	*/  
  }
}

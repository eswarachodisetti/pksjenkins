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
          sh 'docker build -t gcr.io/synt-int-pks-new-lab/poc/poctest:7.0 .'
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
					sh 'docker push gcr.io/synt-int-pks-new-lab/poc/poctest:7.0'
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

pipeline {
  agent any
  stages {
    stage('') {
      steps {
        sh '''pipeline {
	agent any
	tools{
	     maven "MAVEN3"
	     jdk "OracleJDK8"
	}

	stages {
	     stage(\'Fetch code\') {
	         steps{
	            git branch: \'vp-rem\', url: \'https://github.com/nolet7/My_dev.git\'
	         }

	     }

	     stage(\'Build\') {
	          steps{
	             sh \'mvn install -DskipTests\'
	          }
	           post {
	               success {
	                   echo \'Now Archiving it...........\'
	                   archiveArtifacts artifacts: \'**/target/*.war\'
	               }
	           }
	  
	     }

	    test 
	}
}'''
        }
      }

    }
  }
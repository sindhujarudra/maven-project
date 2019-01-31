pipeline 
	{
	    agent any
	    stages{
	        stage('Build')
	        {
	        parallel{
	         stage('One'){
	            steps {
	                sh 'mvn clean package'
	            }
	        }  
	            stage('Two'){
	                  steps{
	                      sh 'mvn  verify'
	                  }
	                }  
	              }
	            post {
	                success {
	                    echo 'Now Archiving...'
	                    archiveArtifacts artifacts: '**/target/*.war'
	                }
	           }
	        }
	     }
	   }

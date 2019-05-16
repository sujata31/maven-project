Pipeline{
    agent any
	
	stages{
	
	    stage('scm checkout'){
		   git 'https://github.com/sujata31/maven-project.git'	
              		
		}
		
		stage('compile stage'){
		
		    steps{
			    withMaven (maven: 'my maven'){
			      sh 'mvn compile'
			    }			
			}
		}
		
		stage('testing stage'){
		
		    steps{
			    withMaven (maven: 'my maven'){
			      sh 'mvn test'
			    }
			}
		}
		
		stage('package stage'){
		
            steps{
                withMaven (maven: 'my maven'){
                  sh 'mvn package'
            	}		
		    }
		}
		
		stage('istall stage'){
		
		    steps{
			    withMaven (maven: 'my maven'){
				  sh 'mvn install'
				}
			}
		
		}
		
		
	}
}
















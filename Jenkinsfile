Pipeline{
    agent any
	
	stages{
	
	    stage('scm checkout'){
		
		    steps{
			   git 'https://github.com/sujata31/maven-project.git'	
            }    		
		}
		
		stage('compile source code'){
		
		    steps{
			    withMaven (maven: 'my maven'){
			      sh 'mvn compile'
			    }			
			}
		}
		
		stage('testing'){
		
		    steps{
			    withMaven (maven: 'my maven'){
			      sh 'mvn test'
			    }
			}
		}
		
		stage('package source code'){
		
            steps{
                withMaven (maven: 'my maven'){
                  sh 'mvn package'
            	}		
		    }
		}
		
		stage('istall source code'){
		
		    steps{
			    withMaven (maven: 'my maven'){
				  sh 'mvn install'
				}
			}
		
		}
		
		
	}
}
















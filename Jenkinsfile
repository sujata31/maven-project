pipeline{
	agent any{
		stages{
			stage('scm checkout'){
				steps{
					git 'https://github.com/sujata31/maven-project.git'}}
			stage('compile source code'){
				steps{
					withMaven (maven: 'my maven'){
					sh 'mvn compile'
					}
				}
			}
			stage('test source code'){
				steps{
					withMaven (maven: 'LocalMaven'){
					sh 'mvn test'
					}
				}
			}
			stage('package source code'){
				steps
					withMaven (maven: 'LocalMaven'){
					sh 'mvn package'
					}
				}
			}
			stage('install sorce code'){
				steps
					withMaven (maven: 'LocalMaven'){
					sh 'mvn install'
					}
				}
			}
}
}
}

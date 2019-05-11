pipeline{
	agent any
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
			stage('install sorce code'){
				steps{
					withMaven (maven: 'my maven'){
					sh 'mvn install'
					}
				}
			}
			stage('deploy to tomcat'){
				steps{
					sshagent(['19e7f38a-3933-4c2a-a04a-b7507eccb72e']) {
					sh 'ssh -o StrictHostKeyChecking=no */target/*.war ec2-user@172.31.33.175:/var/lib/tomcat/webapps']
					}
				}
			}

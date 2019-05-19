pipeline {
    agent any


    stages {
        stage('SCM Checkout'){
          git 'https://github.com/sujata31/maven-project.git'
        }

           stage ('Compile Stage') {

            steps {
                withMaven(maven : 'my maven') {
                    sh 'mvn clean compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'my maven') {
                    sh 'mvn test'
                }
            }
        }


        stage ('install Stage') {
            steps {
                withMaven(maven : 'my maven') {
                    sh 'mvn install'
                }
            }
        }

        stage ('deploy to tomcat') {
             steps {
                 sshagent(['19e7f38a-3933-4c2a-a04a-b7507eccb72e']) {
                 sh 'scp -o StrictHostKeyChecking=no */target/*.war ec2-user@172.31.33.175:/var/lib/tomcat/webapps/'
      } 
}
}
    }
}


pipeline {
	agent any
	tools {
		maven "Maven"
	}
	stages {
// 		stage('Build') {
// 			steps{
// 				//mnvn clean package
// 				sh script: 'mvn clean package'
// 				sh "mvn package -DskipTests=true"
// 			}
// 		}
		stage('Upload War tog Nexus'){
			steps{
                             sh "mvn -X clean deploy > /var/jenkins_home/logs-run-nexus.txt"			
			}
		}
// 		stage("deploy to tomcat"){
// 			steps{
//                                 sh "curl -X GET 192.168.10.136:8081/repository/simpleapp-snapshot/org/springframework/samples/spring-petclinic/2.5.0-SNAPSHOT/spring-petclinic-2.5.0-20211201.082053-8.war --output /var/jenkins_home/.m2/petclinic.war"
//                                 sh "curl --insecure --user root:1234567 -T /var/jenkins_home/.m2/petclinic.war sftp://192.168.10.138/usr/share/tomcat/webapps/"
//                                 sh "mvn tomcat7:redeploy"
// 			}
// 		}
	}
}

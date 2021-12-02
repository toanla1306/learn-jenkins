
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
		// stage('Upload War tog Nexus'){
		// 	steps{
		// 		// script {
		// 		// 	// def version = sh script: 'mvn help:evaluate -Dexpression=project.version -q -DforceStdout', returnStdout: true
		// 		// 	// pom = readMavenPom file: 'pom.xml';
		// 		// 	nexusArtifactUploader artifacts: [
		// 		// 		[
		// 		// 			artifactId: 'spring-petclinic', 
		// 		// 			classifier: '',
		// 		// 			file: 'pom.xml', 
		// 		// 			type: 'war'
		// 		// 		]
		// 		// 	], 
		// 		// 	credentialsId: 'nexus3', 
		// 		// 	groupId: 'org.springframework.samples', 
		// 		// 	nexusUrl: '192.168.10.136:8081', 
		// 		// 	nexusVersion: 'nexus3',
		// 		// 	protocol: 'http', 
		// 		// 	repository: 'simpleapp-snapshot/', 
		// 		// 	version: '2.5.0-SNAPSHOT'
		// 		// }
  //               //sh "mvn -Drepo.id=simpleapp-snapshot -Drepo.login=admin -Drepo.pwd=123 clean deploy"
  //                               sh "mvn -X clean deploy"
		// 		//sh "mvn deploy:deploy-file -DgroupId=org.springframework.samples\
		// 				//-DartifactId=spring-petclinic\
		// 				//-Dversion=2.5.0-SNAPSHOT\
		// 				//-DgeneratePom=true\
		// 				//-Dpackaging=war\
		// 				//-Dfile=pom.xml\
		// 				//-DrepositoryId=simpleapp-snapshot/\
		// 				//-Durl=http://192.168.10.136:8081/repository/simpleapp-snapshot/\
		// 				//"
				
		// 	}
		// }
		stage("deploy to tomcat"){
			steps{
				//sh 'curl -o /usr/local/tomcat/webapps/myapp.war "192.168.10.136:8081/repository/simpleapp-snapshot/org/springframework/samples/spring-petclinic/2.5.0-SNAPSHOT/spring-petclinic-2.5.0-20211201.165740-10.war"'
				sh "mvn archetype:generate -DgroupId=org.springframework.samples -DaritfactId=spring-petclinic -DarchetypeArtifactId=maven-archetype-webapp -DinteractiveMode=false"
                                sh "mvn tomcat7: deploy"
                                //sh 'chmod 777 /var/'
                                //sh 'curl -o /var/myapp123.war "192.168.10.136:8081/repository/simpleapp-snapshot/org/springframework/samples/spring-petclinic/2.5.0-SNAPSHOT/spring-petclinic-2.5.0-20211201.165740-10.war"'
			}
		}
	}
}

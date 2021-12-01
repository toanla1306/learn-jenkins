
pipeline {
	agent any
	tools {
		maven "Maven"
	}
	stages {
		stage('Build') {
			steps{
				//mnvn clean package
				sh script: 'mvn clean package'
				sh "mvn package -DskipTests=true"
			}
		}
		stage('Upload War tog Nexus'){
			steps{
				// script {
				// 	// def version = sh script: 'mvn help:evaluate -Dexpression=project.version -q -DforceStdout', returnStdout: true
				// 	// pom = readMavenPom file: 'pom.xml';
				// 	nexusArtifactUploader artifacts: [
				// 		[
				// 			artifactId: 'spring-petclinic', 
				// 			classifier: '',
				// 			file: 'pom.xml', 
				// 			type: 'war'
				// 		]
				// 	], 
				// 	credentialsId: 'nexus3', 
				// 	groupId: 'org.springframework.samples', 
				// 	nexusUrl: '192.168.10.136:8081', 
				// 	nexusVersion: 'nexus3',
				// 	protocol: 'http', 
				// 	repository: 'simpleapp-snapshot/', 
				// 	version: '2.5.0-SNAPSHOT'
				// }
                //sh "mvn -X -Drepo.id=simpleapp-snapshot -Drepo.login=admin -Drepo.pwd=123 clean deploy | grep settings"
                                sh "mvn -X clean | grep settings"
				sh "mvn deploy:deploy-file -DgroupId=org.springframework.samples\
						-DartifactId=spring-petclinic\
						-Dversion=2.5.0-SNAPSHOT\
						-DgeneratePom=true\
						-Dpackaging=war\
						-Dfile=pom.xml\
						-DcredentialsId=nexus3\
						-DrepositoryId=simpleapp-snapshot/\
						-Durl=http://192.168.10.136:8081/repository/simpleapp-snapshot/\
						"
				
			}
		}
	}
}


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
				def pom = readMavenPom file: 'pom.xml'
				nexusArtifactUploader artifacts: [
					[
						artifactId: 'spring-petclinic', 
						classifier: '', 
						file: 'pom.xml', 
						type: pom.packaging
					]
				], 
				credentialsId: 'nexus3', 
				groupId: 'org.springframework.samples', 
				nexusUrl: '192.168.10.136:8081', 
				nexusVersion: 'nexus3',
				protocol: 'http', 
				repository: 'simpleapp-snapshot/', 
				version: '2.5.0-SNAPSHOT'	
			}
		}
	}
}

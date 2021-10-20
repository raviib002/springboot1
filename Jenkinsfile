def props = readProperties file: "jenkinsfile.properties"

pipeline {
	agent any
        	tools {
        	maven "$MavenName"
    		}
     	stages {
		stage("Build stage") {
		steps {
			sh "mvn clean install package"
			}
		}
		stage('Artifact Stage') {
		steps {
                	nexusArtifactUploader artifacts: [[artifactId: 'Springboottest-A_ID', classifier: '', file: '/var/lib/jenkins/workspace/enkinsfiletest_springboot_master/target/demo-1.0-SNAPSHOT.jar', type: 'jar']], credentialsId: 'ba1a5ce3-b8ed-43ed-8ed3-b387ee6cffa3', groupId: 'Springboottest-G_ID', nexusUrl: '192.168.221.128:8091', nexusVersion: 'nexus3', protocol: 'http', repository: 'maven-snapshots', version: '1.0-SNAPSHOT'
                	nexusArtifactUploader artifacts: [[artifactId: 'Springboottest-A_ID', classifier: '', file: '/var/lib/jenkins/workspace/enkinsfiletest_springboot_master/target/demo-1.0-SNAPSHOT.jar', type: 'jar']], credentialsId: 'ba1a5ce3-b8ed-43ed-8ed3-b387ee6cffa3', groupId: 'Springboottest-G_ID', nexusUrl: '192.168.221.128:8091', nexusVersion: 'nexus3', protocol: 'http', repository: 'maven-releases', version: '2.2.3.RELEASE'
                	}
            	}

	}	
}

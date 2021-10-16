pipeline {
	agent any
        	tools {
        	// Install the Maven version configured as "M3" and add it to the path.
        	maven "maven"
    		}
     	stages {
		stage("Cleaning stage") {
		steps {
			sh "mvn clean install"
			}
		}
		stage("Testing stage") {
		steps {
			sh "mvn test"
			}
		}
		stage("Packageing stage") {
		steps {
			sh "mvn package"
			}
		}
		stage('Artifact Upload') {
		steps {
                	nexusArtifactUploader artifacts: [[artifactId: 'Springboottest-A_ID', classifier: '', file: '/var/lib/jenkins/workspace/enkinsfiletest_springboot_master/target/demo-1.0-SNAPSHOT.jar', type: 'jar']], credentialsId: 'ba1a5ce3-b8ed-43ed-8ed3-b387ee6cffa3', groupId: 'Springboottest-G_ID', nexusUrl: '192.168.221.128:8091', nexusVersion: 'nexus3', protocol: 'http', repository: 'maven-snapshots', version: '1.0-SNAPSHOT'
                	nexusArtifactUploader artifacts: [[artifactId: 'Springboottest-A_ID', classifier: '', file: '/var/lib/jenkins/workspace/enkinsfiletest_springboot_master/target/demo-1.0-SNAPSHOT.jar', type: 'jar']], credentialsId: 'ba1a5ce3-b8ed-43ed-8ed3-b387ee6cffa3', groupId: 'Springboottest-G_ID', nexusUrl: '192.168.221.128:8091', nexusVersion: 'nexus3', protocol: 'http', repository: 'maven-releases', version: '2.2.3.RELEASE'
                	}
            	}

	}	
}

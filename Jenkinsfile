pipeline {
	agent any
        	tools {
        	maven "maven"
    		}
     	stages {
            stage('Properties file') {
            steps {
                script {
                    def props = readProperties file:'jenkinsfile.properties';
                    env['NexusURL_Port'] = props['NexusURL_Port']
                    env['NexusRelRepo'] = props['NexusRelRepo']
                    env['artifactId'] = props['artifactId']
                    env['classifier'] = props['classifier']
                    env['filepath'] = props['filepath']
                    env['type'] = props['type']
                    env['NexusCredentialsId'] = props['NexusCredentialsId']
                    env['groupId'] = props['groupId']
                    env['nexusVersion'] = props['nexusVersion']
                    env['protocol'] = props['protocol']
                    env['NexusSnaRepo'] = props['NexusSnaRepo']
                    env['SnapVersion'] = props['SnapVersion']
                    env['RelVersion'] = props['RelVersion']
                    }                
                }
            }
		stage("Build stage") {
		steps {
			sh "mvn clean install package"
			}
		}
		stage('Artifact Stage') {
		steps {
		nexusArtifactUploader artifacts: [[artifactId: "$artifactId", classifier: "$classifier", file: "/var/lib/jenkins/workspace/"${JOB_NAME}"/target/demo-1.0-SNAPSHOT.jar", type: "$type"]], credentialsId: "$NexusCredentialsId", groupId: "$groupId", nexusUrl: "$NexusURL_Port", nexusVersion: "$nexusVersion", protocol: "$protocol", repository: "$NexusSnaRepo", version: "$SnapVersion"
		nexusArtifactUploader artifacts: [[artifactId: "$artifactId", classifier: "$classifier", file: "/var/lib/jenkins/workspace/"${JOB_NAME}"/target/demo-1.0-SNAPSHOT.jar", type: "$type"]], credentialsId: "$NexusCredentialsId", groupId: "$groupId", nexusUrl: "$NexusURL_Port", nexusVersion: "$nexusVersion", protocol: "$protocol", repository: "$NexusRelRepo", version: "$RelVersion"
                	}
            	}

	}	
}

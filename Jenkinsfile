pipeline {
	agent any
        	tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "maven"
    }
     		stages {
				stage("Cleaning stage") {
						steps {
						sh "mvn clean"
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
			}
		}

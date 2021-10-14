pipeline {
		agent any
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

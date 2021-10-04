@Library('Shared-Library')_
pipeline {
   agent any
    stages {
	 stage ('Clean') {
	        steps {
		       sh '/opt/gradle/gradle-6.4.1/bin/gradle clean'
            }
        }
	stage ('Build') {
	        steps {
		       sh '/opt/gradle/gradle-6.4.1/bin/gradle build'
            }
        }
    stage ('test') {
	        steps {
		       Execute('test')
            }
    	}
	stage ('MavenOps') {
	        steps {
		       sh '/opt/apache-maven-3.6.3/bin/mvn clean install'
            }
        } 
	stage ('Tempertaure conversion') {
		steps {
			temp(98)
		}
	}
    }
}
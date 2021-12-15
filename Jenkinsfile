@Library('Shared-Library.axa')_

import com.app.MavenUtil


def utils = new MavenUtil(this)
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
		      script {
				
				utils.mvn 'clean package'
			  }
            }
        } 
	stage ('Tempertaure conversion') {
		steps {
			temp(98)
		}
	}
    }
}
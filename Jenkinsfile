properties([
	buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '', numToKeepStr: '10')), 
	parameters([
		string(defaultValue: '', description: '', name: 'dummy', trim: false)
	])
])

node {
	stage("Clone") {
		git 'https://github.com/stevancvetkovic/java-app-sample.git'
	}
	
	stage("Build") {
		withMaven(maven: 'maven-3.5.2') {
			sh "mvn clean install"
		}
	}
}

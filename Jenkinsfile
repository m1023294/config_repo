pipeline {
    agent any
    stages {
		stage('load') {
			steps {
				script {
					props = readProperties file: 'pipeline.properties'
					echo 'load success'
				}
			}
		}
		stage('read') {
			steps {
				git url: props.gitUrl,
                branch: props.branch
				echo 'read success'
			}
		}
		stage('scan') {
            steps {
				sh sonarScan
				echo 'scan success'
			}
        }
		stage('build') {
            steps {
				sh mavenBuild
				echo 'build success'
            }
		}
	}
}
pipeline {
    agent { docker { image 'maven:3.3.3' } }
    stages {
		stage('load') {
			steps {
				script {
					props = readProperties file : 'pipeline.properties'
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
		/*stage('scan') {
            steps {
				sh 'mvn sonar:sonar -Dsonar.host.url=http://my58965dns.eastus2.cloudapp.azure.com:9000'
				echo 'scan success'
			}
        }
		stage('build') {
            steps {
				sh 'mvn clean install'
				echo 'build success'
            }
		}*/
	}
}
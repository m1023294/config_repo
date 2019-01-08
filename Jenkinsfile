pipeline {
    agent { docker { image 'maven:3.3.3' } }
    stages {
		stage('scan') {
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
		}
	}
}
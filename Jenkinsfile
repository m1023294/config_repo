pipeline {
    agent { docker { image 'maven:3.3.3' } }
    stages {
		stage('read') {
			steps {
				git url: 'git://github.com/m1023294/app_repo',
                branch: 'master'
				echo 'read success'
			}
		}
		/*stage('scan') {
            steps {
				sh 'mvn sonar:sonar -Dsonar.host.url=http://my58965dns.eastus2.cloudapp.azure.com:9000'
				echo 'scan success'
			}
        }*/
		stage('build') {
            steps {
				sh 'mvn clean install'
				echo 'build success'
            }
		}
	}
}
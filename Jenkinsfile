node('master'){
	
	stage('git checkout'){
	git 'https://github.com/Palanimks/parking_backend.git'
	}
	stage('java build'){
	sh '/opt/maven/bin/mvn clean deploy sonar:sonar -Dsonar.password=admin -Dsonar.login=admin'
	}
	
	stage('Running java backend application'){
	sh 'export JENKINS_NODE_COOKIE=dontKillMe ;nohup java -Dspring.profiles.active=uat -jar $WORKSPACE/target/*.jar &'
	}
	}

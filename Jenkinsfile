pipeline {
	agent any
	stages {
    	stage('Checkout SCM') {
        	steps {
            	git 'https://github.com/nlct2k/JenkinsDependencyCheckTest.git' 
        	}
    	}

    	stage('OWASP Dependency-Check Vulnerabilities') {
  	steps {
    	dependencyCheck additionalArguments: '''
                	-o './'
                	-s './'
                	-f 'ALL'
                	--prettyPrint''', odcInstallation: 'OWASP Dependency-Check Vulnerabilities'
   	 
    	dependencyCheckPublisher pattern: 'dependency-check-report.xml'
  	}
	}
  }
}

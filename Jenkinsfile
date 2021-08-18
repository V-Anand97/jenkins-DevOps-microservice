
//agent any 
  environment {
	  dockerHome = tool "myDocker"
	  mavenHome = tool "myMaven"
	  PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
  }
	   agent {docker {image 'maven: 3.6.3'}}
		stages {
			stage ('Checkout'){
			 steps{	
				 sh 'mvn --version'
				 sh 'docker version'
                echo "Build"
				echo "PATH - $PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "BUILD_URL - $env.BULD_URL"
			 }
			}
			 stage ('Build'){
				 steps {
					 sh "mvn clean compile"
				 }
			 }
			 stage ('Test'){
			 steps{	
		        sh "mvn test"
			 }
			 }
			 stage ('Integration Test'){
			 steps{	
		        sh "mvn failsafe:integration-test failsafe:verify"
			 }
			}
		} 
		post {
			always {
				echo 'Im awesome. I run always'
			}
			success {
				echo 'I run when you are succesful '
			}
			failure {
				echo 'I run when you fail'
			}
		}
		


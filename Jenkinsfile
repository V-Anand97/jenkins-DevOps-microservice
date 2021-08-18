
agent any 

	   
		stages {
			stage ('Build'){
			 steps{	
                echo "Build"
				echo "PATH - $PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "BUILD_URL - $env.BULD_URL"
			 }
			}
			 stage ('Test'){
			 steps{	
		        echo "Test"
			 }
			 }
			 stage ('Integration Test'){
			 steps{	
		        echo "Integration Test"
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
		


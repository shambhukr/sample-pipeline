pipeline {
  agent { label 'master' }

	stages {
	
		stage('First Job') {
			agent {
				label 'master'
			}
			steps {
				script {
					if (( env.BRANCH_NAME == 'master' ) || ( env.BRANCH_NAME == 'develop')) {
						// Checkout the branch.
						//checkout scm
						println "Branch is ${env.BRANCH_NAME}"
						bat 'echo hello'
					}
					else {
						println "Not on master or develop branch doing nothing.branch is ${env.BRANCH_NAME}"
					}
				}
			}
		}
	}
}

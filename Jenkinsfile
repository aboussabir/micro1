pipeline {
	agent any
	stages {
		stage('Hello') {
			steps {
				echo "hello from Jenkinsfile"
			}
		}
		stage('for the fix branch') {
			when {
				branch "fix-*"
			}
			steps {
				ssh '''
				cat README.md
                '''
			}
		}
		stage('for the PR') {
			when {
				branch "PR-*"
			}
			steps {
				echo "this only run for the PRs."
			}
		}

	}
}


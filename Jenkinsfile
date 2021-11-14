pipeline {
	agent none
	stages {
		
		stage('non-parallel stage') {
			agent { 
					label 'master'
					}
			steps {
					echo "this stage will execute first"
				}
			}
			
		stage('run tests') {
			parallel {
				stage ('test on windows') {
				agent {
						label 'windows_node'
					}
				steps {
						echo "task1 on agent"		
				}
			}
			
				stage('test on master') {
				agent {
						label 'master'
					}
				steps {
						echo "task1 on master"			
				}
			}
		}
}
}
}

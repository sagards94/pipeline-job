pipeline {
    agent any
    stages {
		stage('BUILD') {
			steps {
				sh '''
				sleep 5
				echo "This is Build Stage"
				'''

			}
		}
        stage('TEST MULTIPLE STAGES') {
            parallel {
				stage( "TEST ON LINUX MACHINE') {
					steps {
                     	sh '''
						sleep 5
						echo "THIS IS TEST ON LINUX"
						'''
					}
				}
				stage('TEST ON WINDOWS MACHINE') {
					steps {
						sh '''
						sleep 5
						echo "THIS IS TEST ON WINDOWS"
						'''
					}
				}
            }
        }
		
		stage('DEPLOY') {
			parallel {
				stage('SERVER1') {
					steps {
                     	sh 'sleep 5'
					}
				}
				stage('SERVER2') {
					steps {
						sh "sleep 5"
					}
				}
            }
		}
    }
}
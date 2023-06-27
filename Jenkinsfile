pipeline {
    agent { 
        node {
            label 'docker-agent-python'
            }
      }
	  triggers {
		pollSCM 'H/5 * * * *'
	  }
    stages {
        stage('Build') {
            steps {
                echo "Building.."
                sh '''
                echo "doing build stuff.."
				cd myapp
				pip install -r requirements.txt
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing.."
                sh '''
                echo "doing test stuff.."
				cd myapp
				python3 hello.py
				python3 hello.py --name=Val
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver....'
                sh '''
                echo "doing delivery stuff.."
                '''
            }
        }
    }
}

pipeline {
    agent any
    environment{
    	branch1= 'master'
	branch2= 'master'
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing'
		steps{
			script{
			env.BRANCHDEPLOY = input message: 'User input required',
			ok: 'Deploy',
			parameters:[choice(name: 'Branch to deploy', choices: "${branch1}\n${branch2}", description: 'What branch you wont deploy?')]
			}
		}
            }
        }
	stage('Deploy'){
		sh "echo ${BRANCHDEPLOY}"
	}

    }
}

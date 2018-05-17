pipeline {
agent any

environment{
    branch1 = ${GIT_BRANCH##origin/}
}

stages {
    stage('Stage-One') {
        steps {
            script {                                
		env.BRANCHDEPLOY = input message: 'User input required',
                ok: 'Deploy!',
                parameters: [choice(name: 'Branch to deploy', choices: "${branch1}", description: 'What branch you wont deploy?')]
            }
        }
    }
    stage('Stage-Two'){
        steps{
	    sh "echo ${BRANCHDEPLOY}"
        }
    }
}
}

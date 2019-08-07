abcs = ['san', 'testgit2']

pipeline {
    agent any 
    stages {
        stage('Stage 1') {
            steps {
		echo_all(abcs)
            }
        }
    }
}

@NonCPS // has to be NonCPS or the build breaks on the call to .each
def echo_all(list) {
    list.each { item ->
        echo "Hello ${item}"
	sh ‘mkdir ${item}’
		
	 dir(item) {
           git url: "https://github.com/nurhsans/${item}.git"
         }
    }
}
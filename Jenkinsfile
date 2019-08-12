abcs = ['testgit2', 'san']

pipeline {
    agent any 
    stages {
        stage("echoing") {
            echo_stages(abcs)
//        stage('Pulling all code') {
//            steps {
//		echo_all(abcs)
//            }
//        }
        }
    }
}

@NonCPS // has to be NonCPS or the build breaks on the call to .each
def echo_all(list) {
    list.each { item ->
        echo "Hello ${item}"
		
	 dir(item) {
           git url: "https://github.com/nurhsans/${item}.git"
         }
	echo "${item} has been pulled"
    }
}


@NonCPS
def echo_stages(list) {
    list.each { item ->
        echo "stage ${item}"

        stage(item) {
            steps {
                dir(item) {
                    git url: "https://github.com/nurhsans/${item}.git"
                }
            }
        }

    }
}
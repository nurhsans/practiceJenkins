abcs = ['san', 'testgit2']

pipeline {
    agent any 
    stages {
        stage('Stage 1') {
            steps {
                dir('san') {
                    git url: 'https://github.com/nurhsans/san.git'
                }
                dir('testgit2') {
                    git url: 'https://github.com/nurhsans/testgit2.git'
                }
		echo_all(abcs)

                sh('ls')
            }
        }
    }
}

@NonCPS // has to be NonCPS or the build breaks on the call to .each
def echo_all(list) {
    list.each { item ->
        echo "Hello ${item}"
    }
}
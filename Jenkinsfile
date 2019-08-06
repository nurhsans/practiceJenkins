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
                // dir('CombinationBuilder') {
                //     git url: 'https://github.com/AtlasBID/CombinationBuilder.git'
                // }

                sh('ls')
            }
        }
    }
}
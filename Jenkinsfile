abcs = ['testgit2', 'san']


node {
    stage('Pull all codes') {
        if (!params.Jobs.contains("all")) {
            abcs = params.Jobs.tokenize(",")
        }
        for (int i = 0; i < abcs.size(); i++) {
            sh "echo Hello ${abcs[i]}"
            dir("${abcs[i]}") {
                git url: "https://github.com/nurhsans/${abcs[i]}.git"
            }
        }
    }
}
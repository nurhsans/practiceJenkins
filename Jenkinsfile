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
    stage('Print out all pulled jobs') {
        echo "${abcs.size()}"
        for (int i = 0; i < abcs.size(); i++) {
            echo "Hello ${abcs[i]}"
        }
    }
    stage('Get jobs changeSet') {
        def log = "Log: "
        def changeLogSets = currentBuild.getChangeSets()
        echo "Changesets: ${changeLogSets.size()}"

        for (int i = 0; i < changeLogSets.size(); i++) {
            def entries = changeLogSets[i].items
            for (int j = 0; j < entries.length; j++) {
                def entry = entries[j]
                log += "* ${entry.msg} by ${entry.author} \n"
            }
        }

        echo log
    }
}
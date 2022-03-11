   node {
    stage("Prepare") {
        checkout scm
    }

    stage("Build") {
           sh'''npm install'''
            sh'''index.js'''
    }

    stage("Comment") {
        if (env.CHANGE_ID) {
            for (comment in pullRequest.comments) {
                /* Where "automation-user" is the scm account. */
                if (comment.user == "automation-user") {
                    pullRequest.deleteComment(comment.id)
                }
            }
            def date = sh(returnStdout: true, script: "date -u").trim()
            pullRequest.comment("Build ${env.BUILD_ID} ran at ${date}")
        }
    }
} 

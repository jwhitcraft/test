def isStaging = (env.BRANCH_NAME == "master")
def tagRegex = /release-+/
def isProduction = (env.TAG_NAME =~ tagRegex)


node('bazel') {
    properties([disableConcurrentBuilds()])

    stage('scm') {
        print isStaging
        print isProduction
        sh 'printenv'
    }
}

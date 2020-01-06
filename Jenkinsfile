def isStaging = (env.BRANCH_NAME == "master")
def isProduction = (env.TAG_NAME ==~ /release-*/)


node('bazel') {
    properties([disableConcurrentBuilds()])

    stage('scm') {
        print isStaging
        print isProduction
        sh 'printenv'
    }
}

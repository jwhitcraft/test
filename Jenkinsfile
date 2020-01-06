def isStaging = (env.BRANCH_NAME == "master" && env.TAG_NAME == null)
def isProduction = (isReleaseTag(env.TAG_NAME) != null)

node('bazel') {
    properties([disableConcurrentBuilds()])

    stage('scm') {
        print isStaging
        print isProduction
        sh 'printenv'
    }
}

@NonCPS
def isReleaseTag(tagName) {
  def matcher = tagName =~ 'release-(.*)'
  matcher ? matcher[0][1] : null
}

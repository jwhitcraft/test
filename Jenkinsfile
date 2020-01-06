def isStaging = (env.BRANCH_NAME == "master")
def isProduction = (isRelease(env.tagName) != null)


node('bazel') {
    properties([disableConcurrentBuilds()])

    stage('scm') {
        print isStaging
        print isProduction
        sh 'printenv'
    }
}

@NonCPS
def isRelease(tagName) {
  def matcher = tagName =~ 'release-(.*)'
  matcher ? matcher[0][1] : null
}

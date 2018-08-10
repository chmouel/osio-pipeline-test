def jobTimeoutHours = 1

try {
  timestamps{
    timeout(time: jobTimeoutHours, unit: 'HOURS') {
      node {
        stage('Build') {
          openshiftBuild(buildConfig: "openshift-build-test", showBuildLogs: 'true')
        }
      }
    }
  }
} catch (err) {
  echo "in catch block"
  echo "Caught: ${err}"
  currentBuild.result = 'FAILURE'
  throw err
}

# vim: ft=groovy

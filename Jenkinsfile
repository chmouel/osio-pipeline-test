#!/usr/bin/groovy

def currentUser() {
  return openshift.project().replace("-jenkins", "").trim();
}


pipeline {
  agent none
  stages {
    stage('Test init') {
      steps {
        script {
          openshift.withCluster() {
            def currentUser = currentUser()
            echo "Hello from ${openshift.cluster()}'s default project: ${openshift.project()} User ${currentUser}"

            openshift.withProject("${currentUser}") {
              openshift.selector( 'dc', [ environment:'osio-pipeline-test' ] ).delete()
              def fromJSON = openshift.create( readFile( 'osio-pipeline-build.yaml' ) )
            }
          }
        }
      }
    }
  }
}

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
            echo "Hello from ${openshift.cluster()}'s default project: ${openshift.project()} User ${currentUser()}"

            openshift.withProject() {
              openshift.selector( 'dc', [ environment:'osio-pipeline-test' ] ).delete()
            }
          }
        }
      }
    }
  }
}

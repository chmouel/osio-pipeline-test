#!/usr/bin/groovy

def currentUser() {
  return openshift.project().replace("-jenkins", "").trim();
}


pipeline {
  agent any;
  stages {
    stage('Test init') {
      steps {
        script {
          openshift.withCluster() {
            def currentUser = currentUser()
            echo "Hello from ${openshift.cluster()}'s default project: ${openshift.project()} User ${currentUser}"

            openshift.withProject("${currentUser}") {
              openshift.selector( 'dc', [ environment:'osio-pipeline-test' ] ).delete()
              openshift.process(
                readYaml( file: 'osio-pipeline-build.yaml'),
                         "-p",  "MEMORY_LIMIT=600Mi"
              )
            }
          }
        }
      }
    }
  }
}

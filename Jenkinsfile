#!/usr/bin/groovy

pipeline {
  agent none
  stages {
    stage('Test init') {
      steps {
        script {
          openshift.withCluster() {
            echo "Hello from ${openshift.cluster()}'s default project: ${openshift.project()}"

            openshift.withProject() {
              openshift.selector( 'dc', [ environment:'osio-pipeline-test' ] ).delete()
            }
          }
        }
      }
    }
  }
}

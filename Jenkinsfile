#!/usr/bin/groovy

pipeline {
  agent none
  stages {
    stage('Test init') {
      steps {
        //script {
          openshift.withCluster() {
            openshift.withProject() {
              openshift.selector( 'dc', [ environment:'qe' ] ).delete()
            }
          }
        //}
      }
    }
  }
}

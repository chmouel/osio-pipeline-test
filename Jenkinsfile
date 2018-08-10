#!/usr/bin/groovy

pipeline {
  agent none
  stages {
    stage('Test init') {
      steps {
        openshift.selector( 'dc', [ environment:'qe' ] ).delete()
      }
    }
  }
}

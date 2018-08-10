#!/usr/bin/groovy

pipeline {
  agent none
  stages {
    stage('Test init') {
      steps {
        script {
          openshift.selector( 'dc', [ environment:'qe' ] ).delete()
        }
      }
    }
  }
}

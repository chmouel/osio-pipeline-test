#!/usr/bin/groovy

pipeline {
    agent none
    stages {
        stage('Test init') {
          openshift.selector( 'dc', [ environment:'qe' ] ).delete()
        }
    }
}

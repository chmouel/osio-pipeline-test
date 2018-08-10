#!/usr/bin/groovy

pipeline {
    agent none
    stages {
        stage('Test init') {
            steps {
                script {
                    openshift.setLockName("TEST123456")
                }
            }
        }
    }
}

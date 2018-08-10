#!/usr/bin/groovy

pipeline {
    agent none
    stages {
        stage('Test init') {
            steps {
                script {
                    openshift.setLockName(${var-name-that-ideally-includes-job-name-and-run-number})
                }
            }
        }
        stage('Run tests') {
            parallel {
                stage('Test run 1') {
                    steps {
                    }
                }

                stage('Test run 2') {
                    steps {
                    }
                }
            }
        }
    }
}

#!/bin/env groovy
pipeline {
  agent any

  stages {
    stage('Deploy to Artifactory') {
      steps {
        sh 'mvn deploy'
      }
    }
    stage('Deploy to Dev') {
      steps {
        sh 'scp -P 2225 -r script.sh admin@192.168.0.20:/home/admin/.'
        sh 'ssh -p 2225 admin@192.168.0.20 < script.sh'
      }
    }
  }
}

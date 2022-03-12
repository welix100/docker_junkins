pipeline {
  agent {
        docker {
            image 'alpine:latest'
            label 'docker'
        }
    }

  stages {

    stage('Install') {
      steps {
        sh 'ls'
        echo 'Install dependencies'
        sleep 3
      }
    }

    stage('Build') {
      steps {
        sh 'hostname'
        echo 'Build'
        sleep 2
      }
    }

    stage('Test') {
           parallel {
               stage('Unit Test') {
                   steps {
                       echo 'unit test'
                       sleep 2
                   }
               }
               stage('E2E Test') {
                   steps {
                       echo 'unit test'
                       sleep 5
                   }
               }
           }
       }

    stage('Publish') {
      steps {
        sh 'hostname'
        echo 'Publish Artefact on Registery'
        sleep 1
      }
    }
  }
}

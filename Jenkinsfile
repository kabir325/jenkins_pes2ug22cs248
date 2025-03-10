pipeline {
  agent any
  stages {
    stage('Clone repo'){
      steps {
        checkout([$class :'GotSCM',
                  branches:[[name:'*/main']],
                  userRemoteConfigs:[[url:'git@github.com:kabir325/jenkins_pes2ug22cs248.git']]])
      }
    }
    stage('Build') {
      steps(
        build 'PES2UG22CS248-1'
        sh 'g++ main.cpp -o output'
      }
    }
    stage('Test'){
      steps{
        sh './output'
      }
    }
    stage('Deploy'){
      steps{
        echo 'deploy'
      }
    }
  }
  post{
    failure{
      error 'pipeline failed'
    }
  }  
}

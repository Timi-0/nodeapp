pipeline {
    agent any
    stages {
stage('Check Out code from git'){
    steps{
      git branch: 'master', url: "https://github.com/Timi-0/nodeapp.git"
          }
                                 }
            
        stage('check npm version and setup'){
            steps{
            sh 'npm --version'
             sh 'ls -altr'
                sh 'npm config list'
            }
        }
        
    }
    
    
    }

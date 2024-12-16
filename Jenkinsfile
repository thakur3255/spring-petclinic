node('jdk17') {
          stage('SourceCode') {
               //get the code from git repo
               git branch: 'special', credentialsId: 'test1', url: 'https://github.com/thakur3255/spring-petclinic.git'
              }
 
          stage('Build the code') {
               sh 'mvn clean package'
              }

          stage('Archiving and Test Result') {
               junit stdioRetention: '', testResults: '**/surefire-reports/*.xml'
               archiveArtifacts artifacts: '**/*.jar', followSymlinks: false
              }

  }

pipeline {
  agent any
stage('Sonarqube') {
      agent any
      when{
        branch 'master'
      }
      // tools {
       // jdk "JDK11" // the name you have given the JDK installation in Global Tool Configuration
     // }

      environment{
        sonarpath = tool 'SonarScanner'
      }

      steps {
            echo 'Running Sonarqube Analysis..'
            withSonarQubeEnv('sonar-instavote') {
              sh "${sonarpath}/bin/sonar-scanner -Dproject.settings=sonar-project.properties -Dorg.jenkinsci.plugins.durabletask.BourneShellScript.HEARTBEAT_CHECK_INTERVAL=86400"
            }
      }
    }
  stages{
      stage("one"){
          steps{
              echo 'step 1'
              sleep 3
          }
      }
      stage("two"){
          steps{
              echo 'step 2'
              sleep 9
          }
      }
      stage("three"){ 

          when{
            branch 'master'
            changeset "**/worker/**"
            }
              steps{
                  echo 'step 3'
                  sleep 5
              }
          }
      } 

  post{
    always{
        echo 'This pipeline is completed.'
    }
  }
}

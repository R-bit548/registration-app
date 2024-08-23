pipeline{
  agent { label 'Jenkins-Agent' }
  tools {
    jdk 'Java17'
    maven 'Maven3'
    git 'Default'
    }
  stages{
    stage("Cleanup Workspace") {
            steps{
            CleanWs()
            }
    }

    stage("Checkout from SCM"){
            steps {
               git branch: 'main', credentialsId: 'github', url: 'https://github.com/R-bit548/register-app'
        }
    }
    stage("Build Application"){
            steps {
            sh "mvn clean package"
          }
        }
    stage("Test Apllication"){
            steps {
            sh "mvn test"
          }
        }
      }
    }

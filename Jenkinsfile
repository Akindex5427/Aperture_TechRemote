pipeline {
  agent { label 'Jenkins-Agent' }
  tools {
    jdk 'Java17'
    maven 'Maven3'
  }
  stages{
    stage ('Cleanup Workspace'){
      steps {
            cleanWs()
          }
      }

    stage ("Checkout from SCM"){
      steps {
              git branch: 'main', credentialsId: 'github', url: 'https://github.com/Akindex5427/Aperture_TechRemote'
            }
    }

    stage("Build Application"){
       steps {
              sh "mvn  clean package"
            }
      }
    
    stage("Text Application"){
      steps {
              sh "mvn test"
            }
      }    
  }
}

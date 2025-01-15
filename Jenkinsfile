pipeline {
    agent {
        label "jenkins-agent"
    }
    tools {
        jdk 'Java17'
        maven 'Maven3'
    }
    stages {
         stage ("Cleanup Workspace"){
            steps {
                 cleanWs()
             }
         }
         stage ("Checkout from SCM"){
             steps {
                 git branch: 'main', credentialsId: 'github', url: 'https://github.com/nguyenle510/lab_endava'             
             }
         }
         stage ("Build"){
             steps {
                 sh "mvn clean package"            
             }
         }
         stage ("Test"){
             steps {
                 sh "mvn test"            
             }
         }
    }
}

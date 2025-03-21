pipeline {
    agent { label 'Jenkins-worker'}
    tools {
        jdk 'Java21'
        maven 'Maven'
    }
    stages {
        stage("Cleanup Wordkspace"){
            step {
                CleanWs()
            }
        }
        stage("Checkout From SCM"){
            step {
                git branch: 'master', credentialsID: 'Github', url: 'https://github.com/Yuvi-1228/CI-CD-Demo.git'
            }
        }
        stage ("Build Application"){
            step {
                sh "mvn clean package"
            }
        }
        stage ("Test Application"){
            step{
                sh "mvn test"
            }
        }
    }
}

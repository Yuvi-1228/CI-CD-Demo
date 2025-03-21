pipeline {
    agent { label 'Jenkins-worker'}
    tools {
        jdk 'Java21'
        maven 'Maven'
    }
    stages {
        stage("Cleanup Wordkspace"){
            steps {
                CleanWs()
            }
        }
        stage("Checkout From SCM"){
            steps {
                git branch: 'master', credentialsId: 'Github', url: 'https://github.com/Yuvi-1228/CI-CD-Demo.git'
            }
        }
        stage ("Build Application"){
            steps {
                sh "mvn clean package"
            }
        }
        stage ("Test Application"){
            steps{
                sh "mvn test"
            }
        }
    }
}

pipeline {
    agent any

    stages {
        stage("Fetch repository") {
            steps {
                    git 'https://github.com/ChanduReddy3461/hello-world.git'
                }
            }
            stage('Build') { 
            steps {
                 sh 'mvn -f pom.xml clean install'
            }
        }
        
        stage('Test') { 
            steps {
                  sh 'mvn -f pom.xml test'
                  
            }
        }
        stage('deploy code'){
        steps{
        deploy adapters: [tomcat8(credentialsId: '5fa3cfdc-bec0-44e8-b697-228481727fcf', path: '', url: 'http://3.23.111.184:8080/')], contextPath: null, war: '**/*.war'
        }
    }
    }
}

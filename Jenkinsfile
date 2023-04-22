pipeline {
    agent any

    stages {   
        stage('Build with maven') {
            steps {
                sh 'cd SampleWebApp && mvn clean install'
            }
        }
        
             stage('Test') {
            steps {
                sh 'cd SampleWebApp && mvn test'
            }
        
            }
        
        
        stage('deploy to tomcat') {
          steps {
              deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://52.15.211.51:8080/')], contextPath: 'myapplication', war: '**/*.war'
             
              
              
          }
            
        }
            
        }
} 

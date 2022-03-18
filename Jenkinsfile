pipeline {
    agent any
    
    tools{
        maven 'maven3.8'
    }
    
    environment {
                SERVICE_BRANCH = "master"
            }
            
    stages {
        stage('checkout') {
            steps {
                echo "the branch is ${params.branch}"
                git branch: 'main', url: 'https://github.com/microdegree-kannada/mvn_jar.git'
                }
            }
        stage('compile and build'){
          
            steps{
                sh "mvn clean install"
                sh 'echo "The environment variable is ${SERVICE_BRANCH}"'
                }
            }
        stage('Test'){
            steps{
                sh "mvn test"
             }
        }
    }
    post { 
        always { 
            junit '**/target/surefire-reports/TEST-com.microdegree.AppTest.xml'
        }
    }
}


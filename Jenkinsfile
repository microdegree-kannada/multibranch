pipeline {
    agent any
    
    tools{
        maven '3.8.3'
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
                echo "building the enviroment"
                sh 'echo "The environment variable is ${SERVICE_BRANCH}"'
                }
            }
        stage('Test'){
            steps{
                echo "testing the environment"
		echo "this is coming from the feture branch-1 and updated"
             }
        }
    }
    post { 
        always { 
            echo "running this always"
        }
    }
}


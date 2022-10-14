pipeline{
    agent any
    tools { 
        maven 'maven 3.8.6' 
        jdk 'jdk8' 
    }
    stages{
        stage("Sonar Quality Check"){
            steps{
                echo "========executing A========"
                script {
                    withSonarQubeEnv(credentialsId: 'sonar-token') {
                        sh 'mvn sonar:sonar'
                    }
                }
            }
           
        }
    }
    post{
        always{
            echo "========Success========"
        }
       
    }
}
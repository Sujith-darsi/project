pipeline {
    agent any
    stages{
        stage('build project'){
            steps{
                git url:'https://github.com/Sujith-darsi/project.git', branch: "master"
                sh 'mvn clean package'
              
            }
        }
        stage('Build docker image'){
            steps{
                script{
                    sh 'docker build -t sujithdarsi/staragileprojectfinance:v1 .'
                    sh 'docker images'
                }
            }
        }
         
        
     stage('Deploy') {
            steps {
                sh 'sudo docker run -itd --name container180525 -p 8088:8081 sujithdarsi/staragileprojectfinance:v1'
                  
                }
            }
        
    }
}

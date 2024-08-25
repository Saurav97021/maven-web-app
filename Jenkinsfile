pipeline{
    agent any
    tools{
        maven 'M2'
       
    }
    
    stages{
        stage('git checkout'){
            steps{
                git 'https://github.com/Saurav97021/maven-web-app.git'
            }
        }
        stage('maven build'){
            steps{
                sh 'mvn clean package'
            }
        }
        stage('Docker image build'){
            steps{
                sh 'docker build -t firstimg .'
            }
        }
        stage('Docker image deployement'){
            steps{
                sh 'docker run -d -p 9095:8080 firstimg'
            }
        }
    }
}

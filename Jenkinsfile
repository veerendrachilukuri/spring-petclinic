pipeline{
    agent any
    stages{
        stage('Clone'){
            steps{
              git branch: 'feature/2026.10.14', url: 'https://github.com/srinfotechbatch9/spring-petclinic.git'
            }
        }
        stage('Build'){
            steps{
                bat 'mvn install'
            }
        }
        stage('Test'){
 
            steps{
 
                bat 'mvn test'
            }
        }
 
        stage('Generated Tests Reports'){
 
            steps{
                junit 'target/surefire-reports/*.xml'
            }
        }
        stage('Published Artifcats'){
 
            steps{
 
                archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
            }
        }
    }
}
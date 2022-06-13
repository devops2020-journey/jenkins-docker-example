pipeline{
    agent any
    tools{
        maven 'MAVEN'
    }
    stages{
        stage('Build Maven'){
            steps{
                script{
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'git-credential', url: 'https://github.com/devops2020-journey/jenkins-docker-example.git']]])
                sh 'mvn -Dmaven.test.failure.ignore=true clean package'
            }
            }
        }
        stage('Build Docker image'){
            steps{
                script{
                 sh 'docker build -t amit2018jw/java-maven-app-1.0 .'
                }
            }
        }
        stage("push docker image"){
            steps{
                script{
                 withCredentials([string(credentialsId: 'amit2018jw', variable: 'dockerloginpwd')]) {
                   sh 'docker login -u amit2018jw -p ${dockerloginpwd}'
                   sh 'docker push amit2018jw/java-maven-app-1.0'
                  }
                }    
            }
        }
     }
}

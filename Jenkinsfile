pipeline {
    agent any 
    stages {
        stage('clean workspace'){
            steps{
                sh "rm -rf unit_test_with_jenkins"
            }
        }
        
        stage('clone repository and clean it') { 
            steps {
                sh "git clone https://github.com/rkritchat/unit_test_with_jenkins.git"
                sh "mvn clean -f unit_test_with_jenkins"
            }
        }
        stage('Test') { 
            steps {
                sh "mvn test -f unit_test_with_jenkins"
            }
        }
        stage('Deploy') { 
            steps {
                sh "mvn package -f unit_test_with_jenkins"
            }
        }
    }
}

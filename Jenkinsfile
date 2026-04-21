pipeline {
    agent any

    tools {
        maven 'Maven'
        jdk 'JDK21'
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main', url:'',
                credentialsId: 'github-token'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                sh 'mvn package'
            }
        
        
        }
        stage('Run Application') {
            steps {
                sh 'mvn exec:java -Dexec.mainClass="com.example.app.App"'
            }
        }
    }
}

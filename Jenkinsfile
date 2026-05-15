pipeline {
    agent any

    stages {
        stage('Git Checkout') {
            steps {
                echo 'Branch: main https://github.com/mahalleumakant/maven-basic-project.git'
                
            }
        }
        stage('Maven') {
            steps {
                echo 'Building with maven...'
                sh 'mvn clean install'
                sh 'mvn test'
                sh 'mvn package'
                sh 'mvn compile'
                sh 'java -cp target/classes com.cloudnautic.App'
            }
        }
    }

    post {
        failure {
            echo 'Build failed. Please check the logs for details.'
        }
        success {
            echo 'Build succeeded. All tests passed.'
        }
    }
}
pipeline {
    agent {
        docker {
            image 'maven'
            args '-u root -v /home/.m2:/root/.m2'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
    }
}
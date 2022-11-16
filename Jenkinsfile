pipeline {
    agent {
        docker {
            image 'maven:3.8.1-adoptopenjdk-11'
            args '--name maven -v /var/jenkins_home/maven/.m2:/var/jenkins_home/maven/.m2'
        }
    }
    stages {
        stage('maven package') {
      			steps {
        				sh 'mvn -B -Dmaven.test.skip=true -Dmaven.repo.local=/var/jenkins_home/maven/.m2/repository'
      			}
    		}
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
            }
        }
    }
}
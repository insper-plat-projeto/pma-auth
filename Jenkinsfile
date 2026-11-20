pipeline {
    agent any
    stages {
        stage('Dependencies') {
            steps {
                build job: 'account', wait: true
            }
        }
        stage('Build') {
            steps {
                // interface module: install the jar into ~/.m2 for the services that depend on it
                sh 'mvn -B -DskipTests clean install'
            }
        }
    }
}

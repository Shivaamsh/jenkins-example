pipeline {
    agent any

    stages {
        stage ('Compile Stage') {

            steps {
                withMaven(maven : 'maven8593') {
                    sh 'mvn clean compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'maven8593') {
                    sh 'mvn test'
                }
            }
        }
          stage ('Deployment Stage') {

            steps {
                withSonarQubeEnv(envOnly : 'maven8593') {
                    sh 'sonar deploy'
                }
            }
        }
    }
}

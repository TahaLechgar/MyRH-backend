pipeline {

    agent any

     tools {
            maven 'maven-3.9.0'
            jdk 'jdk17'
        }

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean'
                sh 'mvn -e compile'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn -Dtest=UserDetailsServiceTest#should_return_valid_company_matching_email_and_type test'
                sh 'mvn -Dtest=UserDetailsServiceTest#should_return_valid_agent_matching_email_and_type test'
                sh 'mvn -Dtest=UserDetailsServiceTest#should_throw_UsernameNotFoundException test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}

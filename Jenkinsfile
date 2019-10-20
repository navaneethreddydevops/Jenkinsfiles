pipeline {
    agent any
    parameters {
        string (defaultValue: '', description: 'Imagine like 10 parameters here', name: 'buildNumber')
    tools {
        // Yep, everyone was using the same maven and JDK version.
maven 'Maven 3.5.0'
        jdk 'jdk8'
    }
    environment {
        BUCKET='my-app-bucket'
        // ABOUT 15 IDENTICAL ENVIRONMENT VARIABLES
    }
    stages {
        stage("Initialise"){
            steps{
                echo "Config Aws - Yep, everyone does this too"
                sh"""
                    aws do-some-repetitive-shit
                """
                
            }
        }
        stage("Test"){
            when {
                expression {
                    params.buildNumber == ''
                }
            }
            steps{
                echo 'Running Tests'
                sh "Run the same maven command as every build"
                }
            }
            post {
                always {
                    junit 'target/surefire-reports/**/*.xml'
                }
                success {
                    sh "Tell Slack the build went okay"
                }
                failure {
                    sh "Tell Slack the build is knackered"
                }
            }
        }
        stage('Cleanup') {
            when {
                // Do the same conditional logic in every file.
            }
            steps {
                sh "Do the same clean up for every app"
            }
        }
        stage('Packaging') {
            when {
                // Some more conditional logic? Fuck it, why not.
            }
            steps {
                // You guessed it you animals, more of the same.
                sh "Literally run mvn package"
            }
            post {
                failure {
                    sh "A failure condition that has never fired"
                }
            }
        }
        stage(’Push App Version’) {
            when {
                // It’s not complicated enough. MORE CONDITIONALS.
            }
            steps {
                // You bet this is copied and pasted. 
            }    
        }
        stage(’Deploy’) {
            when {
                // Ayyy. It’s not a party without conditional logic.
            }
            steps{
                echo "Deploying cos to dev"
                sh "THE SAME COMMAND EVERY TIME SERIOUSLY OMG"
            }
        }
    }
}

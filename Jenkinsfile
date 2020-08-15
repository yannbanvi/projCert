pipeline {
    agent any
 
    options {
        skipDefaultCheckout(true)
    }
    
    stages {
        stage('Checkout SCM') {
            steps {
                echo '> Checking out the source control ...'
                checkout scm
            }
        }
        
        stage('Installing root dependencies') {
            steps {
                echo '> Running the install_dependencies job'
                build 'install_dependencies'
            }
        }
        
        stage('Installing Docker and Deploying the PHP app') {
            steps {
                echo '> Running the deploy app to test server job'
                build 'deploy-app-to-test-server'
            }
        }
    }
}

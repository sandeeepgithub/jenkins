pipeline {
    agent any
    
    tools {
        nodejs "N-22"
    }


    stages {
        
        stage('Echo version of node') {
            steps {
                sh "npm -v"
            }
            
        }
       
        stage('Install Dependencies') {
            steps {
                // Get the code from GitHub
               git branch: 'main', changelog: false, poll: false, url: 'https://github.com/sandeeepgithub/test-ci-ci.git'

                // Install Maven dependencies
                sh "npm install"  // Skip tests during install
            }
        }

        stage('Test') {
            steps {
                // Run Maven tests.
                sh "npm run test"
            }

        }

    }
}

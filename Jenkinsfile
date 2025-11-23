pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'jenkins', url: 'https://github.com/Ashok220723/sample-jenkins-job.git'
            }
        }
        stage('Build') {
            steps {
                sh '''
                    echo "Hello, Jenkins!"
                    mkdir -p output
                    echo "Build completed at $(date)" > output/build.txt
                '''
            }
        }
        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'output/*.txt', fingerprint: true
            }
        }
    }
}


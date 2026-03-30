pipeline {
    agent any

    environment {
        APP_NAME = "jenkins-demo"
        VERSION = "1.0"
    }

    stages {

        stage('Build') {
            steps {
                sh 'echo "Building $APP_NAME version $VERSION..."'
                sh 'echo "Hiiii - trial - this is building stage"'
            }
        }

        stage('Test') {
            steps {
                sh 'echo "Running tests..."'
                sh 'echo "All tests passed!"'
                sh 'echo "Hiiii - trial - this is testing stage"'
            }
        }

        stage('Deploy to Staging') {
            steps {
                sh 'echo "Deploying to staging server..."'
                sh 'echo "Hiiii - trial - this is deploying to staging stage"'
            }
        }

        stage('Deploy to Production') {
            when {
                branch 'main'
            }
            steps {
                sh 'echo "Deploying to production server..."'
                sh 'echo "Hiiii - trial - this is deploying to production stage"'
            }
        }

    }

    post {
        success {
            echo "Pipeline passed! App is live."
        }
        failure {
            echo "Pipeline failed! Check the logs."
        }
        always {
            echo "Pipeline finished."
        }
    }
}
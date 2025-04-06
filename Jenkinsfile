pipeline {
    agent any

    tools {
        nodejs 'node18'
    }

    environment {
        CI = 'false'
    }

    stages {
        stage('Clone') {
            steps {
                git url: 'https://github.com/Avinash739jecrc/reactapprepo.git', branch: 'main'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'npm test -- --watchAll=false'
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }

        stage('Deploy (Fake)') {
            steps {
                echo 'Simulating deployment...'
                sh 'mkdir -p /tmp/react-deploy'
                sh 'cp -r build/* /tmp/react-deploy/'
                echo 'Build deployed to /tmp/react-deploy (fake prod)'
            }
        }
    }
}

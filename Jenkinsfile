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
                bat 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                bat 'npm test -- --watchAll=false'
            }
        }

        stage('Build') {
            steps {
                bat 'npm run build'
            }
        }

        stage('Deploy (Fake)') {
            steps {
                echo 'Simulating deployment...'
                bat 'mkdir C:\\temp\\react-deploy'
                bat 'xcopy /E /I /Y build\\* C:\\temp\\react-deploy\\'
                echo 'Build deployed to C:\\temp\\react-deploy (fake prod)'
            }
        }
    }
}

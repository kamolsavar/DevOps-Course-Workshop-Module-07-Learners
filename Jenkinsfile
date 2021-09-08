pipeline {
    agent {
        docker { image 'node:14-alpine' }
    }

    stages {
        stage('Build') {
            steps {
                dir('./DotnetTemplate.Web') {
                echo 'Building..'
                sh 'npm install'
                sh 'npm run build'
                }  
            }
        }
        stage('Test') {
            steps {
                dir('./DotnetTemplate.Web') {
                echo 'Building..'
                sh 'npm t'
                }   
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}

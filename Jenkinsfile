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
                slackSend color: "good", message: "Message from Jenkins Pipeline"
                }  
            }
        }
        stage('Test') {
            steps {
                dir('./DotnetTemplate.Web') {
                echo 'Building..'
                sh 'npm t'
                sh 'npm run lint'
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

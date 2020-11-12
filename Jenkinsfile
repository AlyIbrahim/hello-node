
pipeline {
    agent { node { label 'nodejs' } }

    stages {
        stage('Checkout'){
            steps{
                echo "Cloning .."
                git url: "https://github.com/AlyIbrahim/hello-node", branch: "main"
            }
        }
        stage('Build') {
            steps {
                echo 'Building..'
                dir('hello-node'){
                sh "pwd"
                sh "npm install"
            }
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                sh "oc start-build hello-node -F"
            }
        }
    }
}

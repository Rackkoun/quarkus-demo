pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            parallel{
                stage('Test on Windows'){
                    steps{
                        echo "Running tests on Windows"
                    }
                }
                stage('Test on Linux'){
                    steps{
                        echo "Running tests on Linux"
                    }
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

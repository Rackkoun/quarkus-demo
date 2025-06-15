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
        stage('Confirm Deploy to Stagging') {
            steps {
                timeout(time: 60, unit: 'SECONDS'){
                    input(message: 'Okay to Deploy?', ok: 'Let\'s Do it!')
                }
            }
        }
        stage('Stagging') {
            steps {
                echo 'Deploying to stagging...'
                }
            }
        
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}


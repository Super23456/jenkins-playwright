pipeline{
    agent{
        docker{
            image 'mcr.microsoft.com/playwright:lastest'
        }
    }
    stages{
        stage('install playwright'){
            steps{
                sh '''
                    npm install -D playwright/test
                    npx playwright install
                '''
            }
        }
        stage('help'){
            steps{
                sh 'npx playwright test --help'
            }
        }
        stage('run tests'){
            steps{
                sh '''
                    npx playwright test --list
                    npx playwright test
                '''
            }
        }
    }
}
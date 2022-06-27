pipeline{
    agent any
    stages{
        stage("Create Grid"){
            steps{
                bat "docker-compose up -d hub chrome firefox"
            }
        }
        stage("Run Test"){
            steps{
                bat "docker-compose up SeleniumDocker"
            }
        }
    }
    post{
        always{
            archiveArifacts artifacts: 'Artifacts/**'
            bat "docker-compose down"
        }
    }
}
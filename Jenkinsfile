pipeline{
    agent any
    stages{
        stage("Pulling image"){
            steps{
                bat "docker pull samirshh9/selenium-docker"
            }
        }
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
            archiveArtifacts artifacts: 'Artifacts/**'
            bat "docker-compose down"
        }
    }
}
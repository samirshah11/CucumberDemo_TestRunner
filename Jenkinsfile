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
            archiveArtifacts artifacts: 'C:\\Users\\samir\\Desktop\\Artifacts\\', followSymlinks: false
            bat "docker-compose down"
        }
    }
}
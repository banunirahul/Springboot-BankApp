pipeline{
    agent {label "pre-server"}
    stages{
        stage("Fix Permissions") {
            steps {
                echo "Fixing permissions"
                sh 'sudo chmod -R 755 /home/ubuntu/docker/workspace/Bank-app-pipeline/mysql-data'
                sh 'sudo chown -R $(whoami):$(whoami) /home/ubuntu/docker/workspace/Bank-app-pipeline/mysql-data'
            }
        }
        stage("Code clone"){
            steps{
                echo "Starting Code Clone stage"
                git url:"https://github.com/banunirahul/Springboot-BankApp.git",branch:"DevOps"
            }
        }
        stage("Code Build"){
            steps{
                echo "Starting Code Build stage"
                sh "docker build -t bank-app ."
            }
        }
        stage("Code Deploy"){
            steps{
                echo "Starting Code Deploy stage"
                sh "docker compose down && docker compose up -d --build"
            }
        }
    }
}

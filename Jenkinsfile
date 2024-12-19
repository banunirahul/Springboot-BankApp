pipeline{
    agent {label "pre-server"}
    stages{
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

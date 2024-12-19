@Library("sharedLib")_
pipeline{
    agent {label "pre-server"}
    stages{
        stage("Code clone"){
            steps{
                echo "Starting Code Clone stage"
                gitClone("https://github.com/banunirahul/Springboot-BankApp.git","DevOps")
            }
        }
        stage("Code Build"){
            steps{
                echo "Starting Code Build stage"
                echo "docker build -t bank-app ."
            }
        }
        stage("Code Deploy"){
            steps{
                echo "Starting Code Deploy stage"
                echo "docker compose down && docker compose up -d --build"
            }
        }
    }
}

pipeline {
    agent any
    stages{
        stage("Clone Code"){
            steps{
                git url: "git@github.com:talk2maye/node-todo-cicd.git", branch: "working"
            }
        }
        stage("Build and Test"){
            steps{
                sh "docker build . -t mayehunta/todoweb:v1"
            }
        }
        stage("Login and Push image"){
            steps{
                echo "logging in to docker hub and pushing image.."
                sh "docker push mayehunta/todoweb:v1"
                }
            }
        }
            steps{
                sh "docker-compose down && docker-compose up -d"
            }
        }

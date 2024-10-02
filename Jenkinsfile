@Library("Shared") _
pipeline{
    agent {label "vinod"}
    stages{
        stage("Hello"){
            steps{
                script{
                    hello()
                }
            }
        }
        stage("Code"){
            steps{
                script{
                    clone("https://github.com/AmritHimanshu/django-notes-app.git","main")
                }
            }
        }
        stage("Build"){
            steps{
                script{
                    docker_build("himanshu582", "notes-app", "latest")
                }
            }
        }
        stage("Test"){
            steps{
                echo "The code is testing"
            }
        }
        stage("Push to DockerHub"){
            steps{
                script{
                    docker_push("himanshu582", "notes-app", "latest")
                }
            }
        }
        stage("Deploy"){
            steps{
                script{
                    docker_compose()
                }
            }
        }
    }
}
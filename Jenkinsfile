def gv

pipeline {
    agent any
    stages {
        stage("init") {
            steps {
                script {
                    // gv = load "script.groovy"
                    echo "init stage"
                }
            }
        }
        stage("build jar") {
            steps {
                script {
                    echo "building jar"
                    //gv.buildJar()
                }
            }
        }
        stage("build image") {
            steps {
                script {
                    echo "building image"
                    //gv.buildImage()
                }
            }
        }
        stage("deploy") {
            environment{
                AWS_ACCESS_KEY= credentials("aws_access_key")
                AWS_SECRET_KEY= credentials("aws_secret_key")
            }
            steps {
                script {
                    echo "deploying"
                    sh "kubectl create deployment nginx-deployment --image=nginx"
                }
            }
        }
    }   
}
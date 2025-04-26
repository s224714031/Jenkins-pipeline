pipeline {
    agent any
    environment{
            DIRECTORY_PATH = "D:/Master of Data Science/T2 2024/SIT774 Web Technologies and Development/new node_server_template/public_html"
            TESTING_ENVIRONMENT = "QA-Server"
            PRODUCTION_ENVIRONMENT_NAME = "Nadun"
    }

    stages{
        stage ("Build"){
            steps{
                echo "Fetch the source code from the directory path specified by the environment variable"
                echo "Compile the code and generate any necessary artefacts"
            }

            post{
                success{
                    mail to: "nadunhs25@gmail.com",
                    subject: "Build Status Email",
                    body: "Build was successful"
                }
            }

        }
        stage("Test"){
            steps{
                echo "Unit tests" 
                echo "Integration tests"
            }
        }
        stage("Code Quality Check"){
            steps{
                echo "Check the quality of the code"
            }
        }
        stage("Deploy"){
            steps{
                echo "Deploy the application to a testing environment specified by the environment variable"
            }
        }
        stage("Approval"){
            steps{
                echo "Waiting for manual approval..."
                sleep(10)
            }
        }
        stage("Deploy to Production"){
            steps{
                echo "Deploy the code to the production environment: $PRODUCTION_ENVIRONMENT_NAME"
            }
        }
        stage("Complete"){
            steps{
                echo "Completed......"
            }
        }
    }
}

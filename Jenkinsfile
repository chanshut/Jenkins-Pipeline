pipeline{
    agent any
    environment{
        DIRECTORY_PATH ="/Users/chanshutkeung/Documents/Deakin - Data Sicence/2024T1/SIT753 Professional Practice in Information Technology/Week 5/Jenkinsfile"
        TESTING_ENVIRONMENT = "test_envir"
        PRODUCTION_ENVIRONMENT = "Stanley"
    }
    stages{
        stage('Build'){
            steps{
                echo "fetch the source code from the directory path specified by the environment variable"
                echo "compile the code and generate any necessary artifacts"
            }
            post{
                success {
                    mail to: "chanshut@gmail.com",
                    subject: "Build Status Email",
                    body: "Build was successful!"
                }
            }
        }
        stage('Test'){
            steps{
                echo "unit tests" 
                echo "integration tests"
            }
        }
        stage('Code Quality Check'){
            steps{
                echo "check the quality of the code"
            }
        }
        stage('Deploy'){
            steps{
                echo "deploy the application to a testing environment specified by the environment variable"
            }
        }
        stage('Approval'){
            steps{
                 sleep(10)
            }
        }
        stage('Deploy to Production'){
            steps{
                echo "$PRODUCTION_ENVIRONMENT, deployment is done"
            }
        }                
    }
}
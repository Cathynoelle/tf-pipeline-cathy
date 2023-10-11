pipeline {
    agent any

    stages {
        stage ('Starting Point') {
            steps {
                echo "this is the starting point for the terraform pipeline"
            }

        }   
         }


        stage ('Provision Infrastructure') {
            environment {
                AWS_ACCESS_KEY = credentials ("awsaccesskey")
                AWS_SECRET_ACCESS_KEY = credentials ('secretaccesskey')
            }
            steps {
                sh "terraform init"
                sh "terraform apply --auto-approve"
            }
        }

        stage ("Thank you") {
            steps {
                echo "Yay successful TF deployment You're welcome!"
            }
        }
}
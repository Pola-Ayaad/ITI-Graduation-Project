pipeline {
    agent { label'ec2' }

    stages {
        stage('Build') {
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/Pola-Ayaad/Graduation-Project-app-repo.git'

            }
        }
        stage('ci') {
            steps {
                    withCredentials([usernamePassword(credentialsId: 'dockerhub', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]){

                    sh "docker login -u ${USERNAME} -p ${PASSWORD}"
                    sh "docker build .  -t vplma/gcp-terraform:gcp"
                    sh "docker push vplma/gcp-terraform:gcp"
                }
            }    
        }
         stage ('deploy app'){
            steps {
                sh """
                kubectl apply -f deployment.yml
                echo done
            """
            }       
        }
    }
}
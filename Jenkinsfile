pipeline{
    agent any
    enviroment {
        DOCKERHUB_CREDENTIALS=("dockerhub")
    
        stage ("Doker login"){
            steps{
                sh "$DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin"

            }

        }
        stage ("Build & PUSH Dockerfile"){
            steps{
                sh """
                cd Simple-Project
                ansible-playbook ansible-playbook.yml
                """
            }

        }
    }
}
pipeline{
  agent any

  stages{
    stage('Docker Push'){
            steps{
                withCredentials([usernamePassword(credentialsId: 'Docker-Hub', usernameVariable: 'penhass9', passwordVariable: 'DOCKER_PASS')]){
                    sh 
                    echo $DOCKER_PASS | docker login -u $penhass9 --password-stdin
                    docker push ${ubuntu}:latest
                }
            }
        }

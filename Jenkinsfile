
stage('Docker Push') {
    steps {
        withCredentials([
            usernamePassword(
                credentialsId: 'dockerhub-credentials',
                usernameVariable: 'DOCKER_USER',
                passwordVariable: 'DOCKER_PASS'
            )
        ]) {
            sh 
                echo "$DOCKER_PASS" | docker login -u "$DOCKER_USER" --password-stdin
                docker tag ubuntu:latest "$DOCKER_USER/ubuntu:latest"
                docker push "$DOCKER_USER/ubuntu:latest"
                docker logout
        }
    }
}

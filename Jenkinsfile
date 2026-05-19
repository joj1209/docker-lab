node {
    stage('Clone repository') {
        git credentialsId: 'github_access_token', url: 'https://github.com/joj1209/docker-lab.git'
    }

    stage('Build image') {
       dockerImage = docker.build("joj1209/web_count:v1.0")
    }

    stage('Push image') {
        withDockerRegistry([ credentialsId: "docker-access", url: "" ]) {
        dockerImage.push()
        }
    }
}

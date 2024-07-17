node {
    stage('Clone repository') {
        git credentialsId: 'github_access_token', url: 'https://github.com/TSjhkim/jenkins.git'
    }

    stage('Build image') {
       dockerImage = docker.build("kimjihoon0228/jhnote-front:2.0")
    }

    stage('Push image') {
        withDockerRegistry([ credentialsId: "docker-access", url: "" ]) {
        dockerImage.push()
        }
    }
}

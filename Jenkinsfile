pipeline {
    agent any

    stages {
     stage('Building Image') {
        docker.withRegistry('https://registry.hub.docker.com', 'docker_hub') {
            def customImage = docker.build("acc60/nitishrepo:latest")
            customImage.push()
        }
     }

     stage('Run Container') {
        sh 'docker run -d acc60/nitishrepo:latest'
    }
}
}


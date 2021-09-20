node {
    stage("git hub source code checkout"){
        git branch: 'main', credentialsId: 'harishsiddu', url: 'https://github.com/harishsiddu/Siddu.git'
        
    }
    stage("Building the image"){
        sh 'docker build . -t harishsiddu/devarapalli:3.0.0'  
    }
    stage("Pushing  the image"){
        withCredentials([string(credentialsId: 'Dockerhubid', variable: 'DockerHubPass')]) {
           sh 'docker login -u harishsiddu -p ${DockerHubPass}'
        }
        sh 'docker push harishsiddu/devarapalli:3.0.0'
    }

}

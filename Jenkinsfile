pipeline{
    agent any
     stages{
        stage("Code"){
        steps{
            echo "cloning the code"
            git url:"https://github.com/Khaira11/django-notes-app.git" , branch: "main"
    }
        }
stage("Build"){
        steps{
            echo "Buiilding the image"
    sh "docker build -t my-note-app ."
                    }
}
     stage("Push the docker"){
        steps{
            echo "Pushing to docker hub"
           withCredentials([usernamePassword(credentialsId:"dockerhub",passwordVariable:"dockerHubPass",usernameVariable:"dockerHubUser")]){
           sh "docker tag my-note-app ${env.dockerHubUser}/my-note-app:latest"
           sh "docker login -u ${env.dockerHubUser} -p ${env.dockerHubPass}"
           sh "docker push ${env.dockerHubUser}/my-note-app:latest"        
                   }
           }
        }
     
   stage("Deploy"){
        steps{
            echo "Deploy on the container"
            sh " docker-compose down docker-compse up -d"
    }
}
     }
}

pipeline {
    agent any

    stages {
        stage('nodex-codecheck ') {
            steps {
                git credentialsId: 'nerukaadmin', url: 'https://github.com/nerukaadmin/sample-node-js-app.git'
            }
        }
        stage('nodex-docker_build ') {
            steps {
                script{
                  customImage = docker.build("nodex:${env.BUILD_ID}")
                  imageid="nodex:${env.BUILD_ID}"
                  name="nodeapp${env.BUILD_ID}"
                  sh " docker run --name $name -p 81:3000 -d $imageid"
                
                }
        }
        
    }
    
}
}

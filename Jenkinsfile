node {

    stage('Clone repository') {
        checkout scm
    }
    
   
    def app

    stage('Build image') {
        app = docker.build("mif/first-nexus")
    }
    
    stage('Push image') {
        docker.withRegistry('http://193.219.91.103:8083/repository/docker-private/', "myRepo") {
            app.push("${env.BUILD_NUMBER}")
            app.push("latest")
        }
    }
    
}


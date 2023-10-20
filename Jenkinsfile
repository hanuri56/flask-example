node {
     stage('Clone repository') {
         checkout scm
     }
     stage('Build image') {
         app = docker.build("hanuri56/flask-example")
         
     }
     stage('Push image') {
         docker.withRegistry('https://docker.io', 'docker-hub') {
             app.push("${env.BUILD_NUMBER}")
             app.push("latest")
         }
     }
}

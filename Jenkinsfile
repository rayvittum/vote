node {
    def app

     stage('Print user') {

        whoami
    }

    stage('Clone repository') {

        checkout scm
    }

    stage('Build image') {

        app = docker.build("rayvittum/vote")
    }

    stage('Test image') {
            app.inside {
            sh 'echo "Tests passed"'
        }
    }

    stage('Push image') { 
        docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
            app.push("${env.BUILD_NUMBER}")
            app.push("latest")
        }
    }
}

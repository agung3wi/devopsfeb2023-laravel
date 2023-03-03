node {
    
    checkout scm

    // Build 
    stage("Build"){
        docker.image('bentolor/docker-dind-awscli').inside('-u root') {
            sh 'apk add curl'
            sh 'curl -Lo copilot https://github.com/aws/copilot-cli/releases/latest/download/copilot-linux && chmod +x copilot && mv copilot /usr/local/bin/copilot'
            sh 'docker --version'
            sh 'aws --version'
            sh 'copilot -v'
            sh 'docker build -t laravel .'
        }
    }



}

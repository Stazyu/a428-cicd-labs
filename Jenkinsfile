node {
    agent{
        docker {
            label'mydockeragent' // this is optional and can be used to identify your container in
            image 'node:16-buster-slim'
            args '-p 3000:3000'
        }
    }
    stage('Build') {
        try {
            sh 'npm install'
        }
        catch (exc) {
            echo 'Something failed!'
            throw
        }
    }
    stage('Test') {
        try {
            sh './jenkins/scripts/test.sh'
        }
    }
}
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'echo "Hello World"'
                sh '''
                    echo "Mulitline shell steps works too"
                    ls -lah
                '''
            }
        }
    }
}
pipeline {
    agent any
    stages {
        stage('Upload to AWS') {
            steps {
                sh 'echo "Hello World"'
                sh '''
                    echo "Mulitline shell steps works too"
                    ls -lah
                '''

                withAWS(region:'es-west-2') {
                    s3Upload(bucket:"jenkins-bucket-static", path:'/', includePathPattern:'**/*', includePathPattern:'**/*.html', workingDir:'dist')
                }
            }
        }
    }
}
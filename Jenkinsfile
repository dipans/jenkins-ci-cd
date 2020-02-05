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

                withAWS(region:'es-west-2', credentials:'aws-static') {
                    s3Upload(bucket:'jenkins-bucket-static', includePathPattern:'**/*.html', workingDir:'build');
                }
            }
        }
    }
}

pipeline {
    agent any
    stages {
        stage('List HTML') {
            steps {
                sh 'tidy -q -e *.html'
            }
        }
        stage('Upload to AWS') {
            steps {
                withAWS(region:'us-west-2', credentials:'aws-static') {
                    s3Upload(bucket:'jenkins-bucket-static', includePathPattern:'**/*.html');
                }
            }
        }
    }
}

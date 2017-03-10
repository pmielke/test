pipeline {
         agent any
    stages {
        stage('build') {
            steps {
                sh 'python --version'
                sh 'echo hi there'
            }
        }
    }

/* comments? */

    post {
        always {
            echo 'One way or another, I have finished'
            deleteDir() /* clean up our workspace */
        }
        success {
            echo 'I succeeeded!'
        }
        unstable {
            echo 'I am unstable :/'
        }
        failure {
            echo 'I failed :('
        }
        changed {
            echo 'Things were different before...'
        }
    }
}

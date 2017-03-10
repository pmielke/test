pipeline {
         agent any
    stages {
        stage('build') {
            steps {
                sh 'python --version'
                sh 'env'
            }
        }

        stage('Sanity check') {
            steps {
                sh 'whereami.sh'
            }
        }
        
        stage('failure') {
            steps {
                sh '''echo hi;exit 0
                '''
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

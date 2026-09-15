pipeline {
    agent any

    stages {

        stage('Tests') {
            parallel {

                stage('Unit') {
                    steps {
                        sh 'echo Running unit tests'
                    }
                }

                stage('Integration') {
                    steps {
                        sh 'echo Running integration tests'
                    }
                }
            }
        }
    }
}

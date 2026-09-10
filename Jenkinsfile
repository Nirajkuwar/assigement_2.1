pipeline {
    agent any

    stages {

        stage ('checkout') {
            steps {
                git url: 'https://github.com/avi-720/project-by-niraj'
            }
         }

         stage('Build') {
             steps {
                 sh 'npm install'
                 sh 'npm run build'
              }
          }

          stage('parallel Test') {
              parallel {

                  stage('unit Teests') {
                      steps {
                          sh 'npm test'
                      }
                   }

                   stage ('Lint') {
                       steps {
                            sh 'npm run lint'
                       }
                  }
            }
       }
}
post {
   always {
        sh 'rm -rf workspace/*'
        }
    }
}

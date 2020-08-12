pipeline {
   agent any

   stages {
      stage('Verify Branch') {
         steps {
            echo "$GIT_BRANCH"
         }
      }
      stage('Docker Build') {
         steps {
            sh label: '', script: 'sudo docker images -a'
            sh label: '', script: """
               cd azure-vote/
               sudo docker images -a
               sudo docker build -t jenkins-pipeline .
               sudo docker images -a
               cd ..
            """
         }
      }
   }
}

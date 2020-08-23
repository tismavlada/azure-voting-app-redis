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
            sh(script: 'docker images -a')
            sh(script: """
               cd /home/vlada
               docker images -a
               docker build -t jenkins-pipeline .
               docker images -a
               cd ..
            """)
         }
      }
   }
}

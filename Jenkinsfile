pipeline {
   agent any
   stages {
       stage('Build ') {
           steps {
               sh 'mvn --version'
               echo "Build"
           }
       }
        stage('build && SonarQube analysis') {
            agent any 
            steps {
                withSonarQubeEnv('maven') {
                        sh 'mvn clean package sonar:sonar'
                }
            }
        }
      stage('Deploy Code') {
          steps {
               sh """
               echo "Deploying Code"
               """
          }
      }
   }
}

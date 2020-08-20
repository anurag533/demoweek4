pipeline {

      agent any
      environment {
            registry = "anuragsharma02/anuragsharma"
            registryCredential = 'Docker'
            dockerImage = ''
      }
      stages{
        stage('Build') {
          steps{
            bat 'mvn clean package'
          }
        }
        

        
        stage('Building image') {
          steps{
                script {
                      dockerImage= docker.build registry + ":$BUILD_NUMBER"
                }
           }
         }
            
         stage('Deploy our image') {
               steps{
            
                           bat "docker push anuragsharma02/anuragsharma:%BUILD_NUMBER%"
                           }
                     
                }
      }
   
}

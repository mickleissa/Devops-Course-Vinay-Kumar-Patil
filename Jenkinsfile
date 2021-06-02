pipeline{
    //Directives
    agent any
    tools {
        maven 'maven'
    }

    stages {
        // Specify various stage with in stages

        // stage 1. Build
        stage ('Build'){
            steps {
                sh 'mvn clean install package'
            }
        }
        // Stage2 : Testing
        stage ('Test'){
            steps {
                echo ' testing......'

            }
        }
<<<<<<< HEAD
=======

>>>>>>> bc245f009e58bbaf45bf8b89c106a3880fd42b86
        // Stage3 :Deploying 
        stage ('Deploy'){
            steps {
                echo ' Deploying.........'
            }
        }
<<<<<<< HEAD
            }
}
=======
>>>>>>> bc245f009e58bbaf45bf8b89c106a3880fd42b86

             // Stage3 : Publish the source code to Sonarqube
        // stage ('Sonarqube Analysis'){
        //    steps {
        //        echo ' Source code published to Sonarqube for SCA......'
        //        withSonarQubeEnv('sonarqube'){ // You can override the credential to be used
        //             sh 'mvn sonar:sonar'
        //        }
        //
        //    }
        // }
        
        

<<<<<<< HEAD
=======
}
>>>>>>> bc245f009e58bbaf45bf8b89c106a3880fd42b86

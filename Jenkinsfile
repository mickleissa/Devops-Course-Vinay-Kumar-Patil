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
        // Stage3 : Deploy
        stage ('Deploy'){
            steps {
                echo ' deploying......'

            }
        }
        
        //stage3 : Publish the artifat to Nexus
        stage ('Publish to Nexus') {
            steps {
                nexusArtifactUploader artifacts:
                [[artifactId: 'VinayDevOpsLab',
                classifier: '',
                file: 'target/VinayDevOpsLab-0.0.77-SNAPSHOT.war',
                type: 'war']],
                credentialsId: '3d9d30ef-964d-41d0-b514-02ded5bc8c6f',
                groupId: 'com.vinaysdevopslab',
                nexusUrl: '172.20.10.45:8081',
                nexusVersion: 'nexus3',
                protocol: 'http',
                repository: 'VinaysDevOpsLab-SNAPSHOT',
                version: ''
            }            
        }

        // // Stage3 : Publish the source code to Sonarqube
        // stage ('Sonarqube Analysis'){
        //     steps {
        //         echo ' Source code published to Sonarqube for SCA......'
        //         withSonarQubeEnv('sonarqube'){ // You can override the credential to be used
        //              sh 'mvn sonar:sonar'
        //         }

        //     }
        // }

        
        
    }

}
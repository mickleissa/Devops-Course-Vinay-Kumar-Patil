pipeline{
    //Directives
    agent any
    tools {
        maven 'maven'
    }
   environment{
       ArtifactId = readMavenPom().getArtifactId()
       Version = readMavenPom().getVersion()
       Name = readMavenPom().getName()
       GroupId = readMavenPom().getGroupId()
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
        
        //stage4 : Publish the artifat to Nexus
        // i generate it from pipline in jenkins
        stage ('Publish to Nexus') {
            steps {
                 //script {

                //def NexusRepo = Version.endsWith("SNAPSHOT") ? "VinaysDevOpsLab-SNAPSHOT" : "VinaysDevOpsLab-RELEASE"
                nexusArtifactUploader artifacts:
                [[artifactId: '${ArtifactId}',
                classifier: '',
                file: 'target/VinayDevOpsLab-0.0.4-SNAPSHOT.war',
                type: 'war']],
                credentialsId: '3d9d30ef-964d-41d0-b514-02ded5bc8c6f',
                groupId: '${Groupid}',
                nexusUrl: '172.20.10.45:8081',
                nexusVersion: 'nexus3',
                protocol: 'http',
                repository: 'VinaysDevOpsLab-SNAPSHOT',
                version: '${Version}'
            }            
        }
        // Stage 5 : Print some information
        stage ('Print Environment variables'){
                    steps {
                        echo "Artifact ID is '${ArtifactId}'"
                        echo "Version is '${Version}'"
                        echo "GroupID is '${GroupId}'"
                        echo "Name is '${Name}'"
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
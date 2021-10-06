pipeline{
    //Directives
    agent any
    tools {
        maven 'Maven'
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

        // Stage3 : Publish arifact to Nexus
        stage ('Publish to Nexus'){
            steps {
                nexusArtifactUploader artifacts: [[artifactId: 'VinayDevOpsLab', classifier: '', file: 'target/VinayDevOpsLab-0.0.11-SNAPSHOT.war', type: 'war']], credentialsId: '42d66d5c-ae90-43be-9069-80c4b5241c4a', groupId: 'com.vinaysdevopslab', nexusUrl: '172.20.10.150:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'Mousa-DevOpsLab-SnapShot', version: '0.0.11-SNAPSHOT'
                //nexusArtifactUploader artifacts: [[artifactId: 'VinayDevOpsLab', classifier: '', file: 'target/VinayDevOpsLab-0.0.11.war', type: 'war']], credentialsId: '42d66d5c-ae90-43be-9069-80c4b5241c4a', groupId: 'com.vinaysdevopslab', nexusUrl: '172.20.10.150:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'Mousa-DevOpsLab-SnapShot', version: '0.0.11'
            }

        }
    }

        // Stage3 : Publish the source code to Sonarqube
        //stage ('Sonarqube Analysis'){
        //    steps {
        //        nexusArtifactUploader artifacts: [[artifactId: 'VinayDevOpsLab', classifier: '', file: 'target/VinayDevOpsLab-0.0.11.war', type: 'war']], credentialsId: '42d66d5c-ae90-43be-9069-80c4b5241c4a', groupId: 'com.vinaysdevopslab', nexusUrl: '172.20.10.150:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'Mousa-DevOpsLab-SnapShot', version: '0.0.11'
                //echo ' Source code published to Sonarqube for SCA......'
                //withSonarQubeEnv('sonarqube'){ // You can override the credential to be used
                  //   sh 'mvn sonar:sonar'
        //        }

        //    }
        //}


}
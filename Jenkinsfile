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

        // Stage 3 : Publish the artifacts to Nexus
        stage ('Publish to Nexus'){
            steps {
                nexusArtifactUploader artifacts: [[artifactId: 'VinayDevOpsLab', classifier: '', file: 'target/VinayDevOpsLab-0.0.12-SNAPSHOT.war', type: 'war']], credentialsId: '289644b5-4a16-4fb6-86b8-d5bd4531d989', groupId: 'com.vinaysdevopslab', nexusUrl: '10.0.1.251:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'MattsDevOpsLab-SNAPSHOT', version: '0.0.12'
            }
        }

        // Stage3 : Deploying
        stage ('Deploy'){
            steps {
                echo 'deploying....'
            }
        }

        
        
    }

}
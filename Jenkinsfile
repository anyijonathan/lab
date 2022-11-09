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
        
        //stage3 : Publish artifact to Nexus
        stage ('publish to Nexus'){
            steps {
                nexusArtifactUploader artifacts: [[artifactId: 'VinayDevOpsLab', classifier: '', file: 'target/VinayDevOpsLab/0.0.10-SNAPSHOT.war', type: 'war']], credentialsId: '9dbc4413-7435-41e8-9cc5-db9dc3e2a799', groupId: 'com.vinaysdevopslab', nexusUrl: '172.20.10.112', nexusVersion: 'nexus3', protocol: 'http', repository: 'project-snapshot', version: '0.0.10-SNAPSHOT'
            }
        }


        // Stage3 : Deploying
        stage ('Deploy'){
            steps {
                echo ' Deploying........'
                }

            }
        }

        
        
    }


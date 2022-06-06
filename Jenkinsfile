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
            steps{
                nexusArtifactUploader artifacts: [[artifactId: 'AntonsDevOpsLab', classifier: '', file: 'target/AntonsDevOpsLab-0.0.4-SNAPSHOT.war', type: 'war']], credentialsId: '64efc8c1-4d77-4221-9cf0-723672040fb3', groupId: 'com.antonsdevopslab', nexusUrl: '172.20.10.219:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'AntonsDevOpsLab-SNAPSHOT', version: '0.0.4-SNAPSHOT'
            }
        }

        // Stage3 : Publish the artifacts to Nexus
        stage ('Deploy'){
            steps {
               echo 'deploying'
        }

    }
 }
}
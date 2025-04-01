pipeline{
    agent any
    tools{
        maven 'maven3.8.7'
    }
    stages{
        stage('CompileandRunSonarAnalysis'){
            environment{
                SONAR_HOST_URL = 'http://13.218.113.213:9000'
                SONAR_AUTH_TOKEN = credentials('sonarQube')
            }
            steps{
                sh 'mvn clean package sonar:sonar -Dsonar.projectKey=sample_project -Dsonar.host.url=$SONAR_HOST_URL -Dsonar.login=$SONAR_AUTH_TOKEN'
            }
            // steps{
            //    withSonarQubeEnv(installationName: 'sonar-9', credentialsId:'sonarToken') {
            //        sh 'mvn clean package'
                
            //    }
            // }
        }

        // // build docker image
        // stage('BuildDockerImage'){
        //     steps{
        //     withDockerRegistry([credentialsId: "dockerlogin", url:""]){
        //         script{
        //            app =  docker.build("tech365app")
                 
        //         }
        //     }
        //     }
        // }

    //     // push docker image
    //     stage('PushDockerImage'){
    //         steps{
    //         script{

    //             // docker.withRegistry('https://registry.hub.docker.com', 'dockerlogin'){


    //             docker.withRegistry('https://222634367210.dkr.ecr.us-east-1.amazonaws.com', 'ecr:us-east-1:aws-credentials'){
  
    //                 app.push("latest")
    //             }
    //         }
    //     }

    //     }
     }
}

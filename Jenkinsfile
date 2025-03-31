pipeline{
    agent any
    tools{
        maven 'maven3.8.7'
    }
    stages{
        stage('CompileandRunSonarAnalysis'){
            
            steps{
               withSonarQubeEnv(installationName: 'sonar-9', credentialsId:'sonarToken') {
                   sh 'mvn clean package'
                
               }
            }
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

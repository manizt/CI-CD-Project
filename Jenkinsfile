@Library('Shared Library') _

pipeline{
    agent any

    parameters{
        choice(name: 'action', choices: 'create\ndelete', description: 'Choose create/Destroy')
    }


    stages{

        

        stage("Git Checkout"){
            when{ expression { param.action == 'create' } }
            steps{

                gitCheckout(
                    branch:"main",
                    url:"https://github.com/manizt/CI-CD-Project-Jenkins-Sonarqube-Kubernetes-.git"
                
                
                ) 
                }

            }
            
        stage("Unit test maven"){
            when{ expression { param.action == 'create' } }

            steps{
                script{

                    mvnTest()
                                                 
                }

            }
        }
        stage("Integration Test Maven"){
            when{ expression { param.action == 'create' } }
            steps{
                script{

                    mvnIntegrationTest()
                }
            }
        }
        stage("Static Code analysis: Sonarqube"){
            when{ expression { param.action == 'create' } }
            steps{
                script{

                    statiCodeAnalysis()
                }
            }
        }

    


    }


}
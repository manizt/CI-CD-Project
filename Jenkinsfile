@Library('Shared Library') _

pipeline{
    agent any

    parameter{
        choice(name: 'action', choices: 'create\ndelete', description: 'Choose create\Destroy')
    }


    stages{

        when{ expression { param.action == 'create' } }

        stage("Git Checkout"){

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
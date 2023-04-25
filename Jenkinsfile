@Library('Shared Library') _

pipeline{

    agent any

    stages{

        stage("Git Checkout"){

            steps{

                gitCheckout(
                    branch:"main",
                    url:"https://github.com/manizt/CI-CD-Project-Jenkins-Sonarqube-Kubernetes-.git"
                
                
                ) 
                }

            }
            
        stage("Unit test maven"){

            steps{
                script{

                    mvnTest()
                                                 
                }

            }
        }


    }


}
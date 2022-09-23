pipeline{
    agent any
    stages{
        stage("Basic Setup"){
            steps{
                echo "Basic setup start"
                bat "yarn install"
                echo "basic setup completed"
            }
        }
        stage("Run Automated test"){
            parallel{
              stage("CI Machine#1"){
                steps{
                    bat "yarn cypress run --parallel"
                }
              }
               stage("CI Machine#2"){
                steps{
                    bat "yarn cypress run --parallel"
                }
              }
            }
        }
        stage("Report Generation"){
            steps{
                echo "Report generation process running"
            }
        }
        stage("Remove unnecessary files"){
            steps{
                echo "Remove unnecessary files"
            }
        }
    }
}
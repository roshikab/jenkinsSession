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
                    bat "npx cypress run --record --key e4d5b964-9cb5-46d6-bbc4-60f7f295689c"
                }
              }
               stage("CI Machine#2"){
                steps{
                    bat "npx cypress run --record --key e4d5b964-9cb5-46d6-bbc4-60f7f295689c"
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
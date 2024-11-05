pipeline{
    agent any

    stages{
        stage('Checkout'){
            steps{
                git branch: 'main', url:'https://github.com/sglbgqa/lbg-vat-calculator.git'
            }
        }
        stage('SonarQube Analysis'){
            environment{
                scannerHome = tool 'sonarqube'
            }
                steps{
                    withSonarQubeEnv('sonarqube'){
                        sh "${scannerHome}/in/sonar-scanner"
                    }
                }
        }
    }
}
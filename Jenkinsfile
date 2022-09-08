pipeline{
    agent any
    parameters{
        choice( name: 'env', choices: [ 'dev', 'qa'], description: 'Enter Environment')
    }
    stages{
        stage('checkout'){
            steps{
                git credentialsId: 'git-hub', url: 'https://github.com/MilindJawale/webapp.git'
            }
        }
        stage('build'){
            steps{
                sh 'mvn clean install'
            }
        }
        stage('deploy-to-dev'){
            when{
                expression { params.env == "dev" }
            }
            steps{
                deploy adapters: [tomcat9(credentialsId: 'tomcat-passwd', path: '', url: 'http://54.164.64.52:8080/')], contextPath: null, war: '**/*.war'
            }
        }
        stage('deploy-to-qa'){
            when{
                expression{ params.env == "qa" }
            }
            steps{
                deploy adapters: [tomcat9(credentialsId: 'tomcat-passwd', path: '', url: 'http://54.162.98.33:8080/')], contextPath: null, war: '**/*.war'
            }
        }
    }
}

@Library('My-shared-jenkins')

pipeline{
    agent any
    stages{
        stage('first'){
            steps{
                echo 'this is first steps'
            }
        }
        stage('second'){
            steps{
                script{
                    build()
                }
            }
        }
    }
}

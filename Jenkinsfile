@Library('My-shared-jenkins') _
pipeline{
    agent any
    stages{
        stage('first'){
            steps{
                echo 'this is first steps on master'
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

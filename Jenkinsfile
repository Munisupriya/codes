pipeline{
    agent any
    stages{
        stage('download'){
            steps{
                git 'https://github.com/gsureshkiran/my_javaapp.git'
            }
        }
        stage('build'){
            steps{
                sh 'mvn package'
            }
        }
        stage('docker build'){
            steps{
                sh 'docker build -t sureshkiran/helloworld .'
            }
        }
        stage('push image'){
            steps{
                script{
                    withCredentials([string(credentialsId: 'dockerpwd', variable: 'dockerpwd')]) {
                    sh 'docker login -u sureshkiran -p ${dockerpwd}'
                    }
                    sh 'docker push sureshkiran/helloworld'
                    
                }
            }
        }
    }
}

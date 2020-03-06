pipeline {
    agent any
        stages{
            stage('Git Checkout'){
                steps{
                    git 'https://github.com/Deeps333/parking_frontend.git/'
                }
            }
            stage('Build') {
                steps{
                    sh 'npm install'
                    sh 'npm run build'
                    sh 'npm audit fix'
                }
            }
            stage('Deploy'){
                steps{
                    sh 'cp -r $WORKSPACE/build /var/lib/jenkins/home'
                    sh 'curl -u admin:admin http://13.127.72.134:8888/manager/reload?path=/build'
                }
            }
            }
        }

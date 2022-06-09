pipeline {
    agent any

    stages {
        stage('pull code') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/${branch}']], extensions: [], userRemoteConfigs: [[credentialsId: 'zhangsan', url: 'https://github.com/YueBLiangZai/onthewhy.git']]])
                echo 'pull code'
            }
        }
        stage('build project') {
            steps {
                echo 'build project'
            }
        }
        stage('publish project') {
            steps {
                sh '''cd  /var/lib/jenkins/workspace/
                scp -r test_pipeline/ root@192.168.128.133:/root'''
                echo 'publish project'
            }
        }    
    }
}

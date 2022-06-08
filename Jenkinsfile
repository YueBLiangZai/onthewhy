pipeline {
    agent any

    stages {
        stage('pull code') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'zhangsan', url: 'https://github.com/YueBLiangZai/onthewhy.git']]])
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
                echo 'publish project'
            }
        }    
    }
}

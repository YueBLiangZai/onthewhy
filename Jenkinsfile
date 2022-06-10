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
                sshPublisher(publishers: [sshPublisherDesc(configName: 'k8s-master1', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: 'echo "11"', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '/root', remoteDirectorySDF: false, removePrefix: '', sourceFiles: 'test_pipeline/new_test.html')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
                echo 'publish project'
            }
        }    
    }
}

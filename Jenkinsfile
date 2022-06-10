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
                sshPublisher(publishers: [sshPublisherDesc(configName: 'k8s-master1', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '''chmod +x scp_file.sh
./scp_file.sh''', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '/root', remoteDirectorySDF: false, removePrefix: '', sourceFiles: 'new*')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
                echo 'publish project'
            }
        }    
    }
}

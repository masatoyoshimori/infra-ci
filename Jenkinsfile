pipeline {
    agent any
    // 1行コメント
    /*
     * 複数行コメント
     */
    stages {
        stage("-------SCM checkout-------"){
            steps{
                echo 'helloworld'
                checkout([$class: 'GitSCM',
                 branches: [[name: '*/issue#7']],
                 doGenerateSubmoduleConfigurations: false,
                 extensions: [],
                 submoduleCfg: [],
                 userRemoteConfigs: [[url: 'git@github.com:masatoyoshimori/infra-ci.git']]])
            }
                   }

        stage("-------構文チェック-------"){
            steps{
                echo 'helloworld'
            }
        }


         stage("-------lint-------"){
            steps{
                echo 'helloworld'
            }
        }
    }
}

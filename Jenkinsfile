pipeline {
    agent any
    // 1行コメント
    /*
     * 複数行コメント
     */
    stages {
        stage("cleanWs"){
            steps{
                cleanWs()
            }
        }

        stage("SCMcheckout"){
            steps{
                checkout([$class: 'GitSCM',
                 branches: [[name: '*/issue#7']],
                 doGenerateSubmoduleConfigurations: false,
                 extensions: [],
                 submoduleCfg: [],
                 userRemoteConfigs: [[url: 'git@github.com:masatoyoshimori/infra-ci.git']]])
            }
        }

        stage("構文チェック"){
            steps{
                sh 'ansible-playbook --syntax-check site.yml'
            }
        }

         stage("lint"){
            steps{
                sh 'ansible-lint --force-color -v ketchup_nginx.yml'
            }
        }
    }
}

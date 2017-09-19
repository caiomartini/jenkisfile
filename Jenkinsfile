stage('Checkout') {
    node('slave') {
        deleteDir()
        checkout(
            [$class: 'GitSCM', 
            branches: [[name: '*/master']], 
            doGenerateSubmoduleConfigurations: false, 
            extensions: [], 
            submoduleCfg: [], 
            userRemoteConfigs: [[url: 'https://github.com/caiomartini/jenkisfile.git']]])
    }
}
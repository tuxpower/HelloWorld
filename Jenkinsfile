/*

Example workflow to demonstrate simple logic

 */

node() {
    stage name: 'Start Sample Stage'
    echo 'Hello World from pipeline!'

    stage name: 'Code Checkout'
    GIT_BRANCH = 'master'
    GIT_URL = 'https://github.com/Irdeto-Jenkins2/HelloWorld.git'

if(true){
    checkout([$class: 'GitSCM', branches: [[name: GIT_BRANCH]],
              doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'WipeWorkspace']], submoduleCfg: [],
              userRemoteConfigs: [[url: GIT_URL]]])
}
    stage name: 'Version Handling'
    writeFile([file: 'version.txt', text: "${MAJOR}.${MINOR}.${PATCH}.${env.BUILD_NUMBER}"])

    archive('version.txt')
}
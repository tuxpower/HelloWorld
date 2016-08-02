/*

Example workflow to demonstrate simple logic

 */

node() {
    stage name: 'Start Sample Stage'
    echo 'Hello World from pipeline!'

    stage name: 'Code Checkout'
    GIT_BRANCH = 'master'
    GIT_URL = 'git@github.com:Irdeto-Jenkins2/HelloWorld.git'
    checkout([$class: 'GitSCM', branches: [[name: GIT_BRANCH]],
              doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [],
              userRemoteConfigs: [[url: GIT_URL]]])

    stage name:
    writeFile([file: 'version.txt', text: "${MAJOR}.${MINOR}.${PATCH}.${env.BUILD_NUMBER}"])

    archive('version.txt')
}
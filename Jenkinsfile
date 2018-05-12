docker.image('node:6-alpine').withRun('-p 3000:3000') 
{

    stage('Build') 
    {
        checkout(
            [$class: 'GitSCM', 
            branches: [[name: '*/master']], 
            doGenerateSubmoduleConfigurations: false, 
            extensions: [], 
            submoduleCfg: [], 
            userRemoteConfigs: [[url: 'https://github.com/lbrandis/simple-node-js-react-npm-app.git']]]
            )
     }
 }

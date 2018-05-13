docker.image('node:9.11-alpine').inside('-p 3000:3000') 
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
        
        sh 'npm install'
    }
    
    stage('Test')
    {
        sh './jenkins/scripts/test.sh'
    }
 }

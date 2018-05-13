docker.image('node:6-alpine').inside('-p 3000:3000') 
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
        
        sh 'npm cache clean'
        sh 'npm install'
    }
    
    stage('Test')
    {
        sh 'npm test'
    }
 }

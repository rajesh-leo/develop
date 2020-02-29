pipeline {
  agent any
    
  tools {nodejs "node"}
    
  stages {
    stage('Running Unit tests') {
        agent any
            steps {
                    sh "npm run test"
                  }
    }    
    stage ('checkout ')  {
	   agent any
	        steps {
                    checkout([$class: 'GitSCM', branches: [[name: '*/develop']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '06a5a6d2-e487-412d-a018-354f60e1d6db', url: 'https://github.com/rajesh-leo/master.git']]])
                  }
				  
    }
        
    stage('Publish Docker Image to Artifactory') {
        agent any
            steps {
  catchError {
                  
                   sh "cp ~/.npmrc ."
                 sh "timestamp=\$(date +'%Y%m%d%H%M%S') && docker build -t integrations/msteams:\$timestamp . && docker tag integrations/msteams:\$timestamp registry.achievers.cloud/achievers-connect/integrations/msteams:latest && docker tag integrations/msteams:\$timestamp registry.achievers.cloud/achievers-connect/integrations/msteams:\$timestamp && docker push registry.achievers.cloud/achievers-connect/integrations/msteams:latest && docker push regis......
                   
                }
                }
    
    } 
  }
}

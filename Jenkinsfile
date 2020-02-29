pipeline {
  agent any
    
  tools {nodejs "node"}
    
  stages {
    stage('Running Unit  tests') {
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
       =======
  }}

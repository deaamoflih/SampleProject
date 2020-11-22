node {
  
  
  stage('SCM') {
    checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/deaamoflih/SampleProject']]])
                }
  stage('Anlyzing') {
      withMaven {
        withSonarQubeEnv('sonarqube') {
        def mvnHome = tool name: 'mvn', type: 'maven' 
         def scannerHome = tool 'sonarqube';

         
          sh "${mvnHome}/bin/mvn sonar:sonar "
  
                }
                }
  }

    
  }

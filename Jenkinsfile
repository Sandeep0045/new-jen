pipeline {

  agent any
      parameters {
              choice choices: ['plan','apply -auto-approve', 'destroy -auto-approve'], description: '''plan
              apply destroy''', name: 'Commands'
	      string defaultValue: '', description: 'Please fill in the username which you desire to create', name: 'User', trim: true
       }
      // parameters {
      //string defaultValue: '', description: 'Please fill in the username which you desire to create', name: 'User', trim: true
      //}
	environment {
		token = credentials('token1')
	//withCredentials([string(credentialsId: 'token1', variable: 'token')]) {
    // some block
   //}
   }
    stages {
      stage('TF Stages') {
      steps {
    //    sh 'export TF_LOG=TRACE'
    //    sh 'export TF_LOG_PATH=/var/lib/jenkins/jobs/demo-okta11/workspace/Automation.log'
    //    sh 'export TF_VAR_api_token=$token'
    //    sh 'echo $TF_VAR_api_token'
        sh 'pwd'
        sh 'ls -l'
        sh 'export TF_VAR_okta_user=$User'
	sh 'echo $TF_VAR_okta_user'
	sh 'terraform $Commands'
	sh 'ls -l'
     //   sh 'cat Automation.log'
        }
      }      
  } 
}

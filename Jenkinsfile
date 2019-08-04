

parameters { string(name: 'environment', defaultValue: 'prod', description: '') }

try {
  stage('checkout') {
    node {
      cleanWs()
      checkout scm
    }
  }

  // Run terraform init
  stage('hello') {
    node {
       
         if [[ ${environment} == "dev" ]]; then
           echo "hello dev"
        else
           echo "hello prod"
        fi
        
        
      
    }
  }




    
  
  currentBuild.result = 'SUCCESS'
}
catch (org.jenkinsci.plugins.workflow.steps.FlowInterruptedException flowError) {
  currentBuild.result = 'ABORTED'
}
catch (err) {
  currentBuild.result = 'FAILURE'
  throw err
}
finally {
  if (currentBuild.result == 'SUCCESS') {
    currentBuild.result = 'SUCCESS'
  }
}

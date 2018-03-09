// start of pipeline
pipeline {
  // where pipeline job will run
  agent {
    label "master"
  }
  
  // start of stages : build, test, deploy ...
  stages {
    // start of stage : build
    stage('build') {
      // start of running steps inside one stage
      steps {
        // invoke command to build with maven
        sh 'mvn clean install'
      }
    }
    
        // start of deploy state
    stage('deploy') {
      // define step to run
      steps {
        //invoke command to stop tomcat service
        sh 'Tomcat'
        sh 'ping 127.0.0.1 -n 6'
        // copy war file from build target to webapp Tomcat folder
        sh 'cp /y root\\var\\lib\\jenkins\\workspace\\GOL_Pipeline\\gameoflife-web\\target\\gameoflife.war "\\opt\\tomcat\\webapps"'
        //invoke command to start tomcat service      
        sh ' Tomcat'
      }
    } 
  
    
  } 
}


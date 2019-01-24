pipeline { 
    agent any
    tools {
        maven 'localMaven'
    }
      
    stages { 
        stage('Build') { 
            steps { 
               echo 'This is a minimal pipeline.' 
               echo "PATH = ${PATH}"
			   echo "M2_HOME = ${M2_HOME}"
			   echo "maven = ${maven}"
			   withEnv( ["PATH+MAVEN=${tool mvn_version}/bin"] ) {
				  //sh "mvn clean package"
				  sh 'mvn clean package'
			   }
			   
            }
        }
    }
}
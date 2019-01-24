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
			   sh 'mvn clean package'
            }
        }
    }
}
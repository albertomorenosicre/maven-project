pipeline {
    agent any

    parameters 
    {
		string(name: 'tomcat_dev', defaultValue: '18.222.125.0', description: 'Staging Server')
    }

    triggers 
    {
		pollSCM('* * * * *')
     }

	stages
	{
        stage('Build')
        {
            steps 
            {
				bat 'mvn clean package'
            }
            post 
            {
                success 
                {
                    echo 'Now Archiving...'
					archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }

        stage ('Deployments')
        {
			parallel
			{
                stage ('Deploy to Staging')
                {
                    steps 
                    {
						bat 'winscp -i C:/Users/Alberto/Desktop/Trabajo/JAVACursos/Jenkins/tomcat-demo.ppk **/target/*.war ec2-user@${params.tomcat_dev}:/var/lib/tomcat8/webapps'
                    }
                }
            }
        }
    }
}



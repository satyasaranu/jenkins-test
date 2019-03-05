pipeline
{
 agent any
 
 	tools {
 	maven 'latest'
 	}
 	
 	triggers {
 	pollSCM('* * * * *')
 	}
 	
 	stages
 	{
	 	stage('build')
 		{
 		 steps {
 			sh	'mvn package'
 			}
 		}
 		
 		stage('deploy')
 		{
 		 try {
 		 steps {
 		 sh 'scp -r /var/lib/jenkins/workspace/test-pipline/target/jenkins-test.war root@3.95.168.15:/opt/tomcat/webapps'
 			}
 		}
 		catch(exec){
 		 sh 'echo deploy job failed'
 		 }
 		 
 		}
 		
 		
 		stage('post')
 		{
 		steps
 		 {
 		sh 'echo test piplein'
 		}
 		}
 		
	 }
}
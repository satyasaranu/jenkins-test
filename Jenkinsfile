pipeline
{
 agent any
 
 	tools {
 	maven 'latest'
 	}
 	
 	triggers {
 	poolSCM('* * * * *')
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
 		 steps {
 		 sh 'scp -r /var/lib/jenkins/workspace/test-pipline/target/jenkins-test.war root@3.95.168.15:/opt/tomcat/webapps'
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
pipeline
{
 agent any
 	options { buildDiscarder(logRotator(numToKeepStr: '5')) }
 	parameters {
        string(name: 'FIRSTNAME', defaultValue: 'satya', description: 'pleas enter FIRST name')
        string(name: 'LASTNAME', defaultValue: 'saranu', description: 'pleas enter LAST name')
        }
 	tools {
 	maven 'latest'
 	}
 	
 	triggers {
 	pollSCM('* * * * *')
 	}
 	
 
 	stages
 	{
 	   stage('prebuild')
 	   {
 	   steps{
 	   echo "hello ${params.FIRSTNAME}"
 	   echo "hello ${params.LASTNAME}"
 	   }
 	   }
 	   
	 	stage('build')
 		{
 		 
 		 when {
 		     branch 'develop'
 		     }
 		     steps {
 			sh	'mvn package'
 			}
 		}
 		
 		stage('deploy')
 		{
 		 
 		 steps {
 		 script {
 		 try {
 		 	sh 'scp -r /var/lib/jenkins/workspace/test-pipline/target/jenkins-test.war root@3.95.168.15:/opt/tomcat/webapps'
 			}
 
 		catch(exec){
 		 sh 'echo deploy job failed'
 		 }
 		 }
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
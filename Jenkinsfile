pipeline
{
 agent any
 	tools {
 	maven 'latest'
 	}
 	stages
 	{
	 	stage('build')
 		{
 		 steps {
 			sh	'mvn package'
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
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
 			sh	'mvn --version'
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
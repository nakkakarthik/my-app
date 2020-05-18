/*
node {
   stage('SCM Checkout'){
	   git 'https://github.com/nakkakarthik/my-app'
   }
	stage('compile-package'){
		sh 'echo "test"'
			}

}

*/
node {
  withCredentials( [usernamePassword( credentialsId: 'amazon', 
                                      usernameVariable: 'USERNAME', 
                                      passwordVariable: 'PASSWORD')]) {
        // build project
        sh 'mvn clean install'
    }
}

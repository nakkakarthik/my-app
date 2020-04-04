
node {
   stage('Mvn Package'){
	   // Build using maven
	   
	   sh "${mvn} clean package deploy"
   }
	stage('compile-package'){
		sh 'mvn package'
			}

}


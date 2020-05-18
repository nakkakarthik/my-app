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
	
def validateOregPass() {

    boolean passwordmatch = false
    def count = 1
    def failedAttemptsAllowed = 3
    def inputValue1

    while( ! passwordmatch ) {

        inputValue1 = input( id: 'ProdProceed1', message: "Please provide Oregon password to continue", ok: 'Proceed1?', parameters: [password(name: 'password')], submitterParameter: 'submitter')

        withCredentials([string(credentialsId: 'ksm_icprod_oreg', variable: 'ProdPassOre')]) {

            if ("${inputValue1['password']}" == "${ProdPassOre}") {
                println ("${inputValue1['submitter']} user provided correct Oregon password")
                passwordmatch = true
            } else {
                println "${inputValue1['submitter']} user provided incorrect Oregon password. Attempt ${count} out of max ${failedAttemptsAllowed} attempts"
                count++
            }

        }

        if (count == failedAttemptsAllowed+1 ) {
            throw new Exception("${inputValue1['submitter']} user exceeded number of max attempts ${failedAttemptsAllowed}")
        }

    }
}
}


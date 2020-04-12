def WORK_BRANCH = BRANCH_NAME

pipeline {
    agent any

    stages {
        stage('GetChangedAssets') {
            steps {
                echo 'Fetching changed assets..'
                echo "${env.BRANCH_NAME}"
                script {
                      def id = checkout([
	                        $class: 'GitSCM',
                        	branches: [[name: BRANCH_NAME]], 
                        	doGenerateSubmoduleConfigurations: false,
	                        extensions: [[$class: 'CleanBeforeCheckout']], 
                        	submoduleCfg: [], 
                        	userRemoteConfigs: [[credentialsId: 'GitCreds',
                        	url: 'https://github.com/ajitkiid/IS.git']]
                        	])
                echo id.toString()
                    
                    
                }
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}

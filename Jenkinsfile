def WORK_BRANCH = BRANCH_NAME


pipeline {
    agent any

    stages {
        stage('GetChangedAssets') {
            steps {
                echo 'Fetching changed assets..'
                echo "${env.BRANCH_NAME}"
                script {
                    def commitID = GIT_COMMIT.take(5)
                    bat label: '', script: 'md C:\\SoftwareAG\\common\\AssetBuildEnvironment\\source\\'+commitID
                    
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

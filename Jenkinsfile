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
                    def changedAssetsPath = "C:\\SoftwareAG\\common\\AssetBuildEnvironment\\source\\"+commitID
                    bat label: '', script: 'if not exist '+changedAssetsPath+ ' md '+changedAssetsPath
                    def log = bat label: '',returnStdout: true, script:'git log -m -1 --name-only --pretty="format:" '+ GIT_COMMIT
                    echo log
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

pipeline {
    agent any

    environment {
        TEST_SURNAME = "Smith"
        OS_NAME = 'unknown'
    }

    stages {
        stage('Hello') {
            steps {
                script{
                    echo '** This is a test echo statement.'
                    echo "** Hello Mr ${TEST_SURNAME}"
                    $OS_NAME = System.getProperty('os.name')
                    echo "OS is: " + $OS_NAME
                }
            }
        }
        stage('info') {
            steps {
                script{
                    if ($OS_NAME == "Linux") {
                        sh('echo This tests sh.')
                        sh('./info.sh')
                    } else {
                        bat('echo This tests bat.')
                        bat('sh info.sh')
                    }
                }
            }
        }
        stage('appBuild') {
            steps {
                script{
                    if ($OS_NAME == "Linux") {
                        sh('./appBuild.sh')
                    } else {
                        bat('sh appBuild.sh')
                    }
                }
            }
        }
        stage('appRun') {
            steps {
                script{
                    if ($OS_NAME == "Linux") {
                        sh('./appRun.sh')
                    } else {
                        bat('sh appRun.sh')
                    }
                }
            }
        }
    }
}

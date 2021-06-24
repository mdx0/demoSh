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
                }
            }
        }
        stage('info') {
            steps {
                script{
                    sh('echo This tests sh.')
                    sh('./info.sh')
                }
            }
        }
        stage('appBuild') {
            steps {
                script{
                    sh('./appBuild.sh')
                }
            }
        }
        stage('appRun') {
            steps {
                script{
                    sh('./appRun.sh')
                }
            }
        }
    }
}

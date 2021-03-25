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
                    $OS_NAME = System.getProperty('os.name')
                    echo "OS is: " + $OS_NAME
                    if ($OS_NAME == "Linux") {
                        sh('echo This tests sh.')
                        sh('./info.sh')
                        sh('./start.sh')
                        sh('./buildJava.sh')
                    } else {
                        bat('echo This tests bat.')
                        bat('sh info.sh')
                        bat('sh start.sh')
                        bat('sh buildJava.sh')
                    }
                }
            }
        }
        stage('build') {
            steps {
                script{
                    echo 'done.'
                }
            }
        }
    }
}

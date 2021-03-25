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
                        sh('./start.sh')
                    } else {
                        bat('echo This tests bat.')
                        bat('sh info.sh')
                        bat('sh start.sh')
                    }
                }
            }
        }
        stage('buildJava') {
            steps {
                script{
                    if ($OS_NAME == "Linux") {
                        sh('./buildJava.sh')
                    } else {
                        bat('sh buildJava.sh')
                    }
                }
            }
        }
    }
}

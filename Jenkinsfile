pipeline {
    agent any

    environment {
        TEST_SURNAME = "Smith"
    }

    stages {
        stage('build') {
            steps {
                script{
                    def osName = System.getProperty('os.name')
                    echo '** This is a test echo statement.'
                    echo "** Hello Mr ${TEST_SURNAME}"
                    echo "OS is: " + osName
                    if (osName == "Linux") {
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
    }
}

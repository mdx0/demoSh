pipeline {
    agent any

    environment {
        TEST_SURNAME = "Smith"
    }

    stages {
        stage('build') {
            steps {
                script{
                    echo '** This is a test echo statement.'
                    echo "** Hello Mr ${TEST_SURNAME}"
                    echo "OS is: " + System.getProperty('os.name')
                    try{
                        sh('echo This tests sh.')
                        sh('git --version')
                        sh('docker -v')
                        sh('python --version')
                        sh('dir')
                        sh('./start.sh')
                    }catch(e){
                        echo "** Caught an error - regarding sh.\n" + e.toString()
                        bat('echo This tests sh.')
                        bat('git --version')
                        bat('docker -v')
                        bat('python --version')
                        bat('dir')
                        bat('sh start.sh')
                    }
                }
            }
        }
    }
}

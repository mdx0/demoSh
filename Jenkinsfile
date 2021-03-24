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
                    bat('echo This tests sh.')
                    bat('git --version')
                    bat('docker -v')
                    try{
                        sh('python --version')
                    }catch(e){
                        echo "** Caught an error - regarding sh."
                        echo e.toString()
                        bat('python --version')
                    }
                    bat('dir')
                    bat('sh start.sh')
                    echo System.getProperty('os.name')
                }
            }
        }
    }
}

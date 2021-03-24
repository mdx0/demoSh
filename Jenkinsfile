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
                        bat('python --version')
                    }catch(Exception ex){
                        sh('python --version')
                    }
                    echo System.getProperty('os.name')
                }
            }
        }
    }
}

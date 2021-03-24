pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                def surname = 'Smith'
                echo '** This is a test echo statement.'
                echo "** Hello Mr ${surname}"
                bat('echo This tests sh.')
                bat('docker -v')
                bat('python --version')
            }
        }
    }
}

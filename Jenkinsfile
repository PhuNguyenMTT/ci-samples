pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
                    //sh 'docker run -t --rm -v "$(pwd)":/tmp/project katalonstudio/katalon katalonc.sh -projectPath=/tmp/project -retry=0 -statusDelay=15 -testSuiteCollectionPath="Test Suites/TS_RegressionTestCollection" -apiKey="7fbb1fec-3b44-4d6b-a3b1-ceded825f620"'
                sh 'docker run -t --rm -v "$(pwd)":/tmp/project katalonstudio/katalon katalonc.sh -projectPath=/tmp/project -retry=0 -statusDelay=15 -apiKey="7fbb1fec-3b44-4d6b-a3b1-ceded825f620"'
            }
        }
    }
    post {
        always {
            archiveArtifacts artifacts: 'Reports/**/*.*', fingerprint: true
            junit 'Reports/**/JUnit_Report.xml'
        }
    }
}

pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
                    sh 'docker run -t --rm -v "$(pwd)":/tmp/project katalonstudio/katalon katalonc.sh -projectPath=/tmp/project -retry=0 -statusDelay=15 -testSuiteCollectionPath="Test Suites/TS_RegressionTestCollection" -apiKey="743b61b0-8d34-4432-8b92-14089824d2f9"'
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

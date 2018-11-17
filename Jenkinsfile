pipeline {
  agent { label 'linux' }
    stages {
      stage('Unit Tests') {
        steps {
          sh "ant test.xml>junit_report.xml"
        }
      }
    }
}

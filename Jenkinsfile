pipeline {
  agent { label 'linux' }
    stages {
      stage('Unit Tests') {
        steps {
          sh "ant text.xml>junit_report.xml"
        }
      }
    }
}

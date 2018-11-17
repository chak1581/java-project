pipeline {
  agent { label 'linux' }
    stages {
      stage('Unit Tests') {
        steps {
          sh "ant -f test.xml -v>>reports/result.xml"
        }
      }
    }
}

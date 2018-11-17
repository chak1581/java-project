pipeline {
  agent { label 'linux' }
    stages {
      stage('Unit Tests') {
        steps {
          sh "ant java-project/test.xml"
        }
      }
    }
}

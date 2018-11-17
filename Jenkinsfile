pipeline {
  agent { label 'linux' }
    stages {
      stage('Unit Tests') {
        steps {
		  git 'https://github.com/chak1581/java-project.git'
                  sh "ant -f test.xml -v"
		  junit 'reports/result.xml'
        }
      }
        stage('Build') {
         steps {
          sh "ant -f build.xml -v"
        }
      }
	stage('Deploy') {
         steps {
		  sh "aws s3 cp dist/rectangle-${BUILD_NUMBER}.jar s3://chak1581-assignment-3/rectangle-${BUILD_NUMBER}.jar"
        }
      }
	stage('Report') {
         steps {
		 withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: '69938fcf-615c-4329-b14f-4e70a2f79355', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']]) {    
			sh 'aws cloudformation describe-stack-resources --region us-east-1 --stack-name jenkins'    

        }
      }
    }
}

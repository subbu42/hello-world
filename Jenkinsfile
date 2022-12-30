
pipeline {
  agent any
  
//   tools {
//   maven 'M2_HOME'
//   }
  stages {

  stage ('Checkout') {
          steps {
            checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: '69117607-57a8-4cf4-a433-c93d9e9d27f6', url: 'https://github.com/bhavanilakshmimamidi/hello-world.git']]])	 
		}
	}
    stage ('Build'){
      steps {
      sh 'mvn clean package'
            }
    } 
    stage ('DEV Deploy') {
      steps {
      echo "deploying to tomcat "
//      deploy adapters: [tomcat8(credentialsId: 'b985a944-79e6-48bb-9349-57f24de9c433', path: '', url: 'http://3.110.132.162:8090/')], contextPath: 'scmpoc', war: '**/*war'
    	deploy adapters: [tomcat8(credentialsId: '26d16b64-aea5-4398-873e-d06542cd0ccd', path: '', url: 'http://15.206.168.194:8090')], contextPath: 'helloworld', war: '**/*.war'
      }
    }
  }
    
}

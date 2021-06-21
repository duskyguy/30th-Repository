pipeline {
    agent any

    tools {
        maven "MAVEN"
       }

    stages {
        stage('Initialize'){
            steps{
                echo "PATH = ${M2_HOME}/bin:${PATH}"
                echo "M2_HOME = /opt/maven"
            }
        }
        stage('Build') {
            steps {
                dir("/var/lib/jenkins/workspace/Maven-Jenkins222/my-app/my-app") {
                sh 'mvn -B -DskipTests clean package'
                }
            
            }
		}
     }
    post {
       always {
          junit(
        allowEmptyResults: true,
        testResults: '*/test-reports/.xml'
      )
      }
   } 
}

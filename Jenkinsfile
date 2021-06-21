pipeline {
      agent any
      stages {
            stage('Init') {
                  steps {
                        echo 'Hi, this is Anshul from LevelUp360'
                        echo 'We are Starting the Testing'
                        
                  }
            }
            stage('Build') {
                  steps {
                        echo 'Building Sample Maven Project'
                        checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'laluondru', url: 'https://github.com/laluondru/java-app-with-maven.git']]])
                        sh "mvn -Dmaven.test.failure.ignore=true clean package"
                  }
            }
            stage('Deploy') {
                  steps {
                        echo "Deploying in Staging Area"
                  }
            }
            stage('Deploy Production') {
                  steps {
                        echo "Deploying in Production Area"
                  }
            }
      }
}

pipeline {
    agent any

     stages {
        stage('Initialize'){
            steps{
                 echo "PATH = ${MAVEN_HOME}/bin:${PATH}"
                 echo "MAVEN_HOME = /usr/share/apache-maven"
            }
        }
        stage('Build') {
            steps {
                dir("/var/lib/jenkins/workspace/New_demo/my-app/") {
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

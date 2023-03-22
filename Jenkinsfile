pipeline {
    agent any

     stages {
        stage('Initialize'){
            steps{
                sh echo "PATH = ${M2_HOME}/bin:${PATH}"
                sh echo "M2_HOME = /usr/share/apache-maven"
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

pipeline {
    agent any

     stages {
        
        stage('Build') {
            steps {
                dir("/var/lib/jenkins/workspace/java_project/TomcatMavenApp/") {
                sh 'mvn -B -DskipTests clean package'
                }
            
            }
        }
     }
    
}

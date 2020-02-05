
pipeline {
  agent any
  tools {
    maven 'Maven3.6.1'
    jdk 'JDK1.8'
  }
  
  stages {
    stage('build') {
      steps {
        script {
          def javaVersion = 'JDK1.8'
          withEnv(["JAVA_HOME=${tool javaVersion}"]) {
            sh '$JAVA_HOME/bin/java -version'
          }
          def mavenVersion = 'Maven3.6.1'
          withEnv(["MAVEN_HOME=${tool mavenVersion}"]) {
            sh '$MAVEN_HOME/bin/mvn -version'
            echo 'Running build job...'
            sh '$MAVEN_HOME/bin/mvn clean install -DskipTests'
          }
        }
      }
    }
  }
}

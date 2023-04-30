pipeline {
  agent any
  tools {
    gradle 'Gradle'
  }
  stages {
    stage('Build') {
      steps {
        withEnv(['JAVA_HOME=C:\Program Files\Java\jdk-17']) {
          sh 'gradlew.bat build'
        }
      }
    }
    stage('Test') {
      steps {
        withEnv(['JAVA_HOME=C:\Program Files\Java\jdk-17']) {
          sh 'gradlew.bat test'
        }
      }
    }
    stage('Deploy') {
      steps {
        withEnv(['JAVA_HOME=C:\Program Files\Java\jdk-17']) {
          sh 'gradlew.bat deploy'
        }
      }
    }   
  }
}

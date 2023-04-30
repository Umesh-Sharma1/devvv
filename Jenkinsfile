pipeline {
  agent any
  tools {
    gradle 'Gradle'
  }
  stages {
    stage('Build') {
      steps {
        bat 'gradlew.bat build'
      }
    }
    stage('Test') {
      steps {
        bat 'gradlew.bat test'
      }
    }
    stage('Deploy') {
      steps {
        bat 'gradlew.bat deploy'
      }
    }   
  }
}

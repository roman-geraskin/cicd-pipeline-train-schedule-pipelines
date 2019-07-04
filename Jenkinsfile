pipeline {
  agent any
  stages {
    stage ("Build") {
      steps {
        echo "Automated building"
        sh "./gradlew build --no-daemon"
        archiveArtifacts artifacts: "dist/trainSchedule.zip"
      }
    }
  }
}

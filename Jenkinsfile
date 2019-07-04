pipeline {
  triggers {
    githubPush()
  }
  agent any
  stages {
    stage ("Build") {
      when {
        branch 'master'
      }
      steps {
        echo "Automated building"
        sh "./gradlew build --no-daemon"
        archiveArtifacts artifacts: "dist/trainSchedule.zip"
      }
    }
  }
}

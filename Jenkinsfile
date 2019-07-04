properties([
    pipelineTriggers([
      [$class: "GitHubPushTrigger"]
    ])
  ])

pipeline {
  checkout scm
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

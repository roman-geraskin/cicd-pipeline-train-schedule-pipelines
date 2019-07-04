properties([
    pipelineTriggers([
      [$class: "GitHubPushTrigger"]
    ])
  ])

pipeline {
  agent any
  stages {
    checkout scm
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

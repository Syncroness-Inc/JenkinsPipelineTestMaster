pipeline {
  agent any
  stages {
    stage('Prepare/Checkout repos...') {
      steps {
        dir(path: 'repo1') {
          git(url: 'https://github.com/Syncroness-Inc/JenkinsPipelineTest1.git', branch: 'master')
        }

        dir(path: 'repo2') {
          git 'https://github.com/Syncroness-Inc/JenkinsPipelineTest2.git'
        }

      }
    }
    stage('do something') {
      steps {
        bat(script: 'echo:hello world >sample-output.txt', returnStatus: true, returnStdout: true)
      }
    }
    stage('Archive') {
      steps {
        archiveArtifacts(artifacts: '*output*', allowEmptyArchive: true)
      }
    }
  }
}
/* groovylint-disable CompileStatic, DuplicateStringLiteral, NoDef */
pipeline {
  agent any
   stages {
    stage('Test') {
      steps {
        echo 'Unit tests'
      }
    }
    stage('Metadata') {
      steps {
        echo 'Metadata'
        script {
          def enReleaseNotes = input message: 'User input required',
            submitter: 'authenticated'
		}
      }
    }
    stage('Build') {
      steps {
        echo 'Build'
		sh 'node -v'
		sh 'npm -v'
      }
    }
  }
  post {
    always {
      echo 'delete and cleanup after Build'
      //cleanWs()
    }
}
}
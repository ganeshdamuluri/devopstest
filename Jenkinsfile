/* groovylint-disable CompileStatic, DuplicateStringLiteral, NoDef */
pipeline {
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
            submitter: 'authenticated',
            parameters: [[$class: 'TextParameterDefinition', defaultValue: 'New Release with Fixes And Enhancements', description: 'Paste the English release notes', name: 'English']]
        }
      }
    }
    stage('Build') {
      steps {
        echo 'Build'
		sh 'node -v'
		sh 'npm -v'
		echo $JAVA_HOME
      }
    }
  }
  post {
    always {
      echo 'delete and cleanup after Build'
      cleanWs()
    }
  }
}
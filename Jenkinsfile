pipeline {
  agent any
  stages {
    stage('check out') {
      steps {
        git(url: 'https://github.com/cameronkinsella/maven-samples-A6.git', branch: 'master')
      }
    }

    stage('bisect') {
    	steps {
        sh "git bisect start 9337327c4c5b9ec58666af6e0274034eb0a2dbaf 98ac319c0cff47b4d39a1a7b61b4e195cfa231e5"
		    sh "git bisect run mvn clean test"
		    sh "git bisect reset"
    	}
    }

  }
  tools {
    maven 'DHT_MVN'
    jdk 'DHT_SENSE'
  }
}

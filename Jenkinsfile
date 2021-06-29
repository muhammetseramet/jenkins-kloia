pipeline {
    agent { label 'master' }
    stages {
        stage('build') {
            steps {
                echo "Hello World!"
                echo "Hello Kloia Bootcamp"
            }
        }
        stage('Deploy') {
            steps {
            echo "Deploy Stage"
            }
        }
        stage('run-parallel-branches') {
          steps {
            parallel(
             stage('Test On Windows') {
                    agent {
                        label "windows"
                    }
                    steps {
                        bat "run-tests.bat"
                    }
                    post {
                        always {
                            junit "**/TEST-*.xml"
                        }
                    }
                }
                stage('Test On Linux') {
                    agent {
                        label "linux"
                    }
                    steps {
                        sh "run-tests.sh"
                    }
                    post {
                        always {
                            junit "**/TEST-*.xml"
                        }
                    }
                }
            )
          }
        }
    }
}

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
                  a: {
                    echo "This is branch a"
                  },
                  b: {
                    echo "This is branch b"
                  }
                )
              }
         }
    }
}

pipeline {
  agent any
    stages {
        stage ("clone the repo") {
          steps {
            sh "git clone url"
          }
        }
      stage ("build the code") {
          steps {
            sh "docker build -t demoimg ."
          }
      }

      stage ("deploy the index.html") {
          agent slave1
        {
          
        }
        steps {
            sh "docker run -d -p 8080:8080 demoimg"
        }
      }
      
    }
}

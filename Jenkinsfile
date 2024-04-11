pipeline {
  agent {
    label 'master'
  }
    
    stages {
        stage("clone the repo") {
          steps {
            cleanWs()
            sh "git clone https://github.com/survasebhagyashree/demorepo.git"
          }
        }
      stage('Initialize') {
        def dockerHome = tool 'myDocker'
        env.PATH = "${dockerHome}/bin:${env.PATH}"
    }

      stage("build the code") {
          steps {
            sh "docker build -t demoimg ."
          }
    }

      stage("deploy the index.html") {
          agent  {
            label 'slave1'
          }
        steps {
            sh "docker run -d -p 8080:8080 demoimg"
        }
      }
    }
}

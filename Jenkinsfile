pipeline {
  agent {
    docker {"image httpd"}
    stages {
        stage ("clone the repo") {
          steps {
            sh "git clone url"
          }
        }
      stage ("deploy code") {
          steps {
            sh "cp index.html /var/www/html"
          }
      }
      
    }
}



pipeline {
    agent any
    environment {
        PATH = "/usr/local/opt/python/libexec/bin:/usr/local/opt/go/libexec/bin/:/usr/local/opt/go/libexec/bin/:/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin:/usr/bin:/bin:/usr/sbin:/sbin:/usr/local/bin:$PATH"
      }
    stages {
        stage('Build') {
            steps {
                sh "echo $PATH"
                //sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Notify') {
            steps {
                sh "curl -X POST -H 'Content-type: application/json' --data '{\"text\":\"This is a line of text.\"}  ${SLACK}"
            }
        }
    }
}


  
}

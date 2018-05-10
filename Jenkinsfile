

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
                script {
                    if (env.BUILD_NUMBER.toInteger() % 2 == 0 ) {
                                sh "khwdlkwehjlkwhewjk"
                        } else {
                                echo 'I execute elsewhere'
                        }
                }
            }
        }
        stage('Notify') {
            steps {
                sh "echo ${currentBuild.currentResult}"
            }
        }
    }
    post { 
        always { 
                sh "curl -X POST -H 'Content-type: application/json' --data '{\"text\":\"Build completed with ${currentBuild.currentResult}.\"}'  ${SLACK}"
        }
    }
}


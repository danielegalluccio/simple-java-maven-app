pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh "export PATH=/usr/local/opt/python/libexec/bin:/usr/local/opt/go/libexec/bin/:/usr/local/opt/go/libexec/bin/:/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin:/usr/bin:/bin:/usr/sbin:/sbin:/usr/local/bin:$PATH"
                sh "echo $PATH"
                sh 'mvn -B -DskipTests clean package'
            }
        }
    }
}

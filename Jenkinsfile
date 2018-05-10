import groovy.json.JsonOutput
// Add whichever params you think you'd most want to have
// replace the slackURL below with the hook url provided by
// slack when you configure the webhook
def notifySlack(text, channel) {
    //def slackURL = 'https://hooks.slack.com/services/xxxxxxx/yyyyyyyy/zzzzzzzzzz'
    def payload = JsonOutput.toJson([text      : text,
                                     channel   : channel,
                                     username  : "jenkins",
                                     icon_emoji: ":jenkins:"])
    sh "curl -X POST --data-urlencode \'payload=${payload}\' ${SLACK}"
}

pipeline {
    agent any
    environment {
        PATH = "/usr/local/opt/python/libexec/bin:/usr/local/opt/go/libexec/bin/:/usr/local/opt/go/libexec/bin/:/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin:/usr/bin:/bin:/usr/sbin:/sbin:/usr/local/bin:$PATH"
      }
    stages {
        stage('Build') {
            steps {
                sh "echo $PATH"
                sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Notify') {
            steps {
                notifySlack "The build completed with $result" "test"
            }
        }
    }
}

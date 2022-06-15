pipeline {
    agent any // any none //	Defining agent none at the top-level of the Pipeline ensures that an Executor will not be assigned unnecessarily. Using agent none also forces each stage section to contain its own agent section.
    stages {
        stage('Example Build') {
//             agent { docker 'maven:3.8.1-adoptopenjdk-11' }
            steps {
                echo 'Hello, Maven'
//              sh 'sudo docker --version'
                sh '''
                 echo "Executing Tests"
                 URL=`curl -s "http://localhost:4040/api/tunnels/command_line" | jq -r '.public_url'`
                 echo $URL
                 RESULT=`curl -sPOST "https://api.ghostinspector.com/v1/suites/[redacted]/execute/?apiKey=[redacted]&startUrl=$URL" | jq -r '.code'`
                 echo $RESULT
      '''
            }
        }
        stage('Example Test') {
//             agent { docker 'openjdk:8-jre' }
            steps {
                echo 'Hello, JDK'
//                 sh 'java -version'
            }
        }
    }
}

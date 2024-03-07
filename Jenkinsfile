pipeline{
  agent any
  stages {
          stage('Clone repository'){
            steps {
              checkout([$class: 'GitSCM',
              branches: [[name: '*/main']],
              userRemoteConfigs: [[url: 'https://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@github.com/Meenalbagare/PES2UG21CS289_Jenkins']]])
            }
          }
    stage('Build'){
        steps {
          build 'PES2UG21CS289-1'
          sh 'g++ main.cpp -o output'
        }
    }
    stage('Deploy') {
        steps {
            echo 'deploy'
        }
    }
}
post{
  failure{
    error 'Pipeline failed'
  }
}
}

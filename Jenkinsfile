pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Build phase is starting here..'
        sh 'echo "No build process has been defined yet!"'
      }
    }
    stage('Test') {
      steps {
        echo 'Test phase is starting here..'
        timestamps() {
          timeout(unit: 'MINUTES', time: 15) {
            git(url: 'https://github.com/zoltanors/Hello.git', branch: 'master', changelog: true, poll: true)
            sh '''source /home/vagrant/.rvm/scripts/rvm
ruby test.rb'''
          }

        }

      }
    }
    stage('Finish') {
      agent any
      steps {
        echo 'Well done!'
      }
    }
  }
}
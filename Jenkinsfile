
node {
  checkout scm
    stage('Build Solution') { 
        agent {
            docker {
                docker.withServer('tcp://52.91.18.62:4243') 
                def myEnv = docker.build 'my-environment:snapshot'
                args '-v ${PWD}:/usr/src/app -w /usr/src/app'
                reuseNode true
            }
        }
        steps {
            sh 'make test'
        }
    }
}

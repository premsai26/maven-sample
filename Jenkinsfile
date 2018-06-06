
node {
  checkout scm
    stage('Build Solution') { 
        agent {
            docker {
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

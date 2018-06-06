
node {
  checkout scm
    
    docker.withServer('tcp://52.91.18.62:4243') {
  def myEnv = docker.build 'my-environment:snapshot'
  myEnv.inside {
    sh 'make test'
  }
}
}

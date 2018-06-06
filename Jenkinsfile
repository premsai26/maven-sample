node {
    def app

    stage('Clone repository') {
        /* Let's make sure we have the repository cloned to our workspace */

        checkout scm
    }
    
    
     stage('Create Docker Image') {
    dir('webapp') {
        docker.withServer('tcp://52.87.126.181:4243') {
      docker.build("premsai26/maven-sample:${env.BUILD_NUMBER}")
        }
    }
  }

    stage('Run Tests') {
    try {
      dir('webapp') {
        sh "mvn test"
        docker.build("arungupta/docker-jenkins-pipeline:${env.BUILD_NUMBER}").push()
      }
    } catch (error) {

    } finally {
      junit '**/target/surefire-reports/*.xml'
    }
    }
}

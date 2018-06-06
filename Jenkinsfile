node {
    def app

    stage('Clone repository') {
        /* Let's make sure we have the repository cloned to our workspace */

        checkout scm
    }

    stage('Build image') {
        dir('webapp') {
        /* This builds the actual image; synonymous to
         * docker build on the command line */
        docker.withServer('tcp://52.87.126.181:4243') {
            app = docker.build("premsai26/maven-sample")
            
            }}
      }
    }
     stage('Run Tests') {
    try {
      dir('webapp') {
        sh "mvn test"
        
      }
    } catch (error) {

    } finally {
      junit '**/target/surefire-reports/*.xml'
    }
  }

 }

node {
    def app

    stage('Clone repository') {
        /* Let's make sure we have the repository cloned to our workspace */

        checkout scm
    }

    stage('Build image') {
        /* This builds the actual image; synonymous to
         * docker build on the command line */
        docker.withServer('tcp://52.91.18.62:4243') {
            app = docker.build("premsai26/maven-sample")
            docker.image('premsai26/maven-sample').inside {
  sh 'cat /etc/alpine-release'
}
            app.inside {
            sh 'clean compile'
        }
      }
    }
     }

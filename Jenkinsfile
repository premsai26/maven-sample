node {
    def app

    stage('Clone repository') {
        /* Let's make sure we have the repository cloned to our workspace */

        checkout scm
    }

    stage('Build image') {
        /* This builds the actual image; synonymous to
         * docker build on the command line */
        docker.withServer('tcp://54.165.49.142:4243') {
            app = docker.build("premsai26/maven-sample")
            app.inside {
            sh 'pwd'
        }
      }
    }
    stage('Test image') {
        /* Ideally, we would run a test framework against our image.
         * For this example, we're using a Volkswagen-type approach ;-) */

       
    }
 }

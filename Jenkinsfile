node {
    def app

    stage('Clone repository') {
        /* Let's make sure we have the repository cloned to our workspace */

        checkout scm
    }

    stage('Build image') {
        /* This builds the actual image; synonymous to
         * docker build on the command line */
        docker.withServer('tcp://52.87.126.181:4243') {
            app = docker.build("premsai26/maven-sample")
            app.pull()
            checkout scm
       stage(‘Build’) {
      sh ‘docker run — privileged -t -v $(pwd):/home/jenkins  -w /go/src/git.example.com/group/registrysync group/go-builder-base-image:master bash -c “go get && go build”’
        }
      }
    }
   }

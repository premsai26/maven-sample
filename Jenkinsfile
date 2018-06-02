pipeline {
    agent none
    stage ('Checkout') {
        agent any
        steps {
            git(
                url: 'https://github.com/premsai26/maven-sample.git'
            )
        }
    }
    stage ('Build') {
        agent {
            dockerfile {
            filename 'Dockerfile'
        }
        steps {
            sh ' uname-a'
        }
}
    }
   
}

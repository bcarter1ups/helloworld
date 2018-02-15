node {
    def app

    stage('Clone repository') {
        /* Let's make sure we have the repository cloned to our workspace */

        checkout scm
    }

    stage('Build image') {
        /* This builds the actual image; synonymous to
         * docker build on the command line */

        app = docker.build("bcarter1/helloworld")
    }

    stage('Test image') {
        /* Ideally, we would run a test framework against our image.
         * For this example, we're using a Volkswagen-type approach ;-) */

        app.inside {
            sh 'echo "Node version: "' 
            sh 'node -v'
            sh 'echo "Tests passed"'
        }
    }

    stage('start container') {
        /* docker run -d -p '8000:8000' 'bcarter1/helloworld:latest' --name 'helloworld' */
    }
}

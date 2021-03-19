node {
    stages {
        stage('Pull From GitHub') {
            steps {
                checkout scm
            }
        }

        stage('Stop Running Containers') {
            steps {
                // stop any running containers
                sh 'docker container stop $(docker ps -a -q)'
            }
        }

        stage('Execute Docker Steps') {
            steps {
                docker.withRegistry('https://registry.hub.docker.com', 'dockerHub') {

                    // build the image
                    def customImage = docker.build("briantlam/project1")

                    // Push the image to the custom Registry
                    customImage.push()

                    // Run the container on port 3000
                    customImage.run("-p 3000:3000")
                }
            }
        }
    }
}
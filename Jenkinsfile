node {
    checkout scm

    docker.withRegistry('https://registry.hub.docker.com', 'dockerHub') {

        def customImage = docker.build("briantlam/project1")

        /* Push the container to the custom Registry */
        customImage.push()

        /* Run the container on port 3000 */
        customImage.withRun("-p 3000:3000") {}
    }
}
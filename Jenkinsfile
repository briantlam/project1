node {
    checkout scm

    docker.withRegistry('https://registry.hub.docker.com', 'dockerHub') {

        def customImage = docker.build("briantlam/project1")

        /* Push the container to the custom Registry */
        customImage.push()
    }
}
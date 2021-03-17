node {
    checkout scm

    /* stop the container if it's already running */
    docker ps -q --filter ancestor=briantlam/project1 | xargs docker stop
    
    docker.withRegistry('https://registry.hub.docker.com', 'dockerHub') {

        def customImage = docker.build("briantlam/project1")

        /* Push the container to the custom Registry */
        customImage.push()

        /* Run the container on port 3000 */
        customImage.run("-p 3000:3000")
    }
}
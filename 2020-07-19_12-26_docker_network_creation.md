
THIS SHOWS HOW TO CREATE CUSTOM NETWORKS AND HOW TO CONNECT TO THEM
USING THE DOCKER RUN COMMANDS

- docker network ls
    lists all the networks on the docker engine

- docker network inspect
    - similar to docker inspect, it shows all the configs of the
      network

    - docker network inspect bridge
        - this is an example of using the inspect command

        - it will showing all the properties of the network called
          "bridge"
        
        - bridge is the default network that is created when docker
          is installed

        - this command will show all the containers connected to the
          birdge network
    
- docker network create [--driver]
    - this is used to create custom docker networks on the host

    - docker network create front_end_net
        - this will create a custom network called "front_end_net"

    - docker network create --help
        - this gives all the options that can be used with the docker
          network create command

    - docker run --name app1 -dit --network front_end_net nginx
        - the command will do the following:
            - create a container from the nginx image
            - name the container app1
            - attach it to the "front_end_net" network
        

- docker network connect [custom_network] [container_name]
    - this will create NIC on a container and attach it to a custom
      network

    - docker network connect front_end_net app2
        - this command will connect the app2 container and connect it
        to the custom network front_end_net
    
- docker network disconnect [custom_network] [container_name]
    - this will disconnect the container from a given network

    - docker network disconnect front_end_net app2
        - this command will disconnect the app2 container from the custom network front_end_net
    
# creating a docker private registry using docker-compose and assigning a volume for data storing 
YOU CAN SIMPLY CREATE YOUR OWN DOCKER PRIVATE REGISTRY JUST BY RUNNING THE COMMAND " # docker-compose up " IN THE TERMINAL.
YOU CAN CHECK IT BY TYPING " # docker container ls "

# registry will be running at 127.0.0.1:5000

# basic steps for running a private docker registry 
-----> run the registry image -----


$ docker run -d -p 5000:5000 --name docker-registry -v $(pwd)/registry-data:/var/lib/registry registry

------> Retag an existing image and pushing it into your new private registry -------------


FOR EXAMPLE


$ docker pull hello-world   //or any other image
$ docker tag hello-world 127.0.0.1:5000/test_image   //any name you want to assign after 127.0.0.1:5000/
$ docker push 127.0.0.1:5000/test_image


--- // this will be completed with similar to this result type ---

 The push refers to repository [127.0.0.1:5000/hello-world]
af0b15c8625b: Pushed 
latest: digest: sha256:92c7f9c92844bbbb5d0a101b22f7c2a7949e40f8ea90c8b3bc396879d95e899a size: 524

#  

# Intro To Kasm

Kasm is a tool which utilizes docker containers to create a secure platform for streaming various applications. Kasm workspaces pride themselves in their utilisation as a Remote Browser Isolation (RBI) solution, Desktop as a service (DaaS) and Open-Source Intelligence (OSINT).

Kasm can be used for many use cases, from browsing privatisation, to creating remote labs for ethical hackers and penetration testers, to simply spinning up and running development pipelines.

Kasm offers a variety of services, is easy to setup and use, and offers the possibility of having multiple accounts for concurrent users, which can all have statistics collected by an administrator who can control access within the Kasm workspace, this can be utilised particularly well at an enterprise level where employers may wish to check that their employees are not utilising the tool searching for inappropriate content in the workplace.

Kasm is a fully remote solution, this means there is no need for a VPN or any need to install client-side software on each individual machine, as such it is easily scalable and maintainable.

We can launch applications inside our Docker containers, for sure, we can also stream our existing X Socket to a Docker container, this is the socket which allows access to X Window System and X Server communication, X Server manages the X clients and does the work in terms of managing input and display devices as well as performing the requested operations. X Server simplifies programming as the programs themselves need not be aware of our hardware details, instead, they can simply rely on X Server, mounting this to our container allows us to launch GUI applications. This approach would still be on our host machine, unless we set it up on a remote server with a registered DNS or utilised a VPN. It would also require us to build a new compose file per case, and would mean much more setup if we wanted to use this from other machines.

Kasm simplifies this, by installing Kasm on a remote server we can access it from anywhere via a handy browser plugin. Kasm workspaces will setup a multitude of applications by default, including Ubuntu, Postman, VSCode and more... we can then add other images as we please through a simple easy-to-use GUI. This is also great for managing access to our workspaces.

___

Learn About the X Window System [Here](https://en.wikipedia.org/wiki/X_Window_System)


[<< Home](./README.md)
# Browser Isolation

Web isolation removes the risk of web browsing outside of enterprise. Kasm acts as an intermediary between your machine and the internet, all web activity is conducted within docker containers running in an isolated environment with a interface streaming to the browser. Kasm is zero-trust by default, meaning that there is no "default" trust on the network and permissions must be manually assigned.

To set up browser isolation we simply navigate to our browsers extension store, and install the Kasm - Open In Isolation extension. It is then simply a case of configuring the "options" within this extension to point to your Kasm instance.

We must then select a default workspace within our Kasm Admin panel.

# Users And Groups

In Kasm we can setup multiple users and groups just like we would on a local machine or network. We can then control what specific users and groups are allowed to use and access. We can do this through the handy GUI provided by Kasm workspaces. Since Kasm is zero trust if groups overlap the rule of the lowest priority will always take precedence.

# Monitoring and Logging

Kasm provides monitoring and logging statistics on the dashboard. If we wish to dig deeper it is possible to use docker commands from our remote server to view the containers as they are spun up, from this you can log specific containers using ````docker log```` track stats with ````docker stats```` or run any other docker commands you could normally.

# Web Filtering

Kasm provided web filtering, which allows us to filter content for our users. This allows us to restrict access to ensure users are only accessing the things we want them to. Kasm supports both blacklist and whitelist filter policies.

# Persistent Profiles

Sometimes we might want our profiles to persist, rather than completely destroying our instance after usage, we may want to save some content. We can access this from the Admin section -> images, we can select our desired image and select "edit".

We then scroll down to the persistent profile path option. This path can be anything we want on the server, if the path does not already exist, it will be created. The important part is to pass a dynamic username: ```/kasm/profiles/Ubuntu/{username}```

You must then add a setting in the group settings section and enable ```allow_persistent_profiles```
with a value of ```true```.

Persistent profiles can be deleted and reset at your leisure, you can also launch a container with or without your persistent profile on a per-launch basis. These are especially useful for running additional OS for playing with Linux features, or even devving in a linux VM.

# Staging

Staging, much like staging in dev, allows us to speed up our container launches, it ensures commonly used images are ready to go at a moments notice. To configure staging we go to the staging record within the Admin section. We then need to switch our domain within the Zones section to our IP address.

# Running as Root

At times you may need root privileges. For instance when installing new packages in a Linux environment.
Kasm makes this simple, simply navigate to the image you wish to use as root, and edit the image. Scroll
down to the Docker Run Config Override JSON field. This becomes as simple as declaring the user within this JSON.

<pre>
<code>
{
    "hostname":"kasm",
    "user":"root"
}
</code>
</pre>
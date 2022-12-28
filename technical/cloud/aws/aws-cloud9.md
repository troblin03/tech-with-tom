# Cloud9

AWS Cloud9 is a _cloud-based_ IDE. It comes with an intergrated debugger, text editor, and built in terminal pre-configured with AWS Command Line Interface.

It works by configuring an _environment_ at startup. This method allows you to keep specific sessions for different projects.

Another big advantage is that you are able to pair programme in real time. Two people can be in front of the same code helping debug or similar.

## Startup

1. Designate a name and (optionally) a description for your Cloud9 instance
2. Choose the environment type. Your Cloud9 instance can run on an entirely new EC2 instance or run on a remote server (eg on-premises)
3. Designate the required instance. Ranges from micro to large (or custome). You specify the amount of RAM and vCPU you require
4. Specify the platform and the time to idle (how long it will take for the environment to auto-hibernate to save costs).

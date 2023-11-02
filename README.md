# graphql-tools

**A Black Hat GraphQL lab in a container.**

## Install

### Clone the repository
`git clone https://github.com/danieldavidson/graphql-tools.git && cd graphql-tools`

### Build the Docker image
`docker build -t graphql-tools - < graphql-tools/Dockerfile`

### Create an interactive container from the image
`docker run --rm -it graphql-tools`

## Use
The `-it` options instruct Docker to create an interactive `bash` shell in the container.

The Black Hat GraphQL lab tools have been installed in the `/tools` directory of the container.

Assuming that you've launched the [Damn Vulnerable GraphQL Application](https://github.com/dolevf/Damn-Vulnerable-GraphQL-Application) according to the installation instructions, the vulnerable app will be accessible from the graphql-tools container using the container host's IP address (in the following example that's `192.168.1.27`).

```
user@ba668db4e141:/tools$ cd graphw00f/
user@ba668db4e141:/tools/graphw00f$ python3 main.py -d -t http://192.168.1.27:5013

                +-------------------+
                |     graphw00f     |
                +-------------------+
                  ***            ***
                **                  **
              **                      **
    +--------------+              +--------------+
    |    Node X    |              |    Node Y    |
    +--------------+              +--------------+
                  ***            ***
                     **        **
                       **    **
                    +------------+
                    |   Node Z   |
                    +------------+

                graphw00f - v1.1.12
          The fingerprinting tool for GraphQL
           Dolev Farhi <dolev@lethalbit.com>
  
[*] Checking http://192.168.1.27:5013/
[*] Checking http://192.168.1.27:5013/graphql
[!] Found GraphQL at http://192.168.1.27:5013/graphql
```

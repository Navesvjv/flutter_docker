## Flutter + Docker + VS Code
Dockerize flutter apps with vs code.

## Installation

Install the [Docker](https://www.docker.com/)

Install the [VS Code](https://code.visualstudio.com/) and add two extensions:

- [Docker](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-docker)
- [Remote Development](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack)

## Usage
1. Clone this repository.

2. Click on this icon created by Remote development (*lower left corner*).

	![Remote Development](https://github.com/Navesvjv/url_images/blob/main/flutter_docker/remote_devlopment.png?raw=true)
3. Select the option ``Remote-Containers: Open Folder in Container``.
4. Select the root directory that contains the Dockerfile and click Open to start building the container.
5. Wait for the download and settings to complete.
6. Create your projects inside the ``workspace`` folder.

## Understanding files
### Dockerfile

	FROM ubuntu:20.04
	
Create a ubuntu based container

	RUN apt update && apt install -y curl git unzip xz-utils zip libglu1-mesa openjdk-8-jdk wget

- curl git unzip xz-utils zip libglu1-mesa is required by Flutter SDK
- openjdk-8-jdk is required by Android SDK
- wget will be used for downloading some Android tools
	

## Contributing
Pull requests are always welcome.  
👊
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

```Dockerfile
FROM ubuntu:20.04
```
Create a ubuntu based container.


```Dockerfile
RUN apt update && apt install -y curl git unzip xz-utils zip libglu1-mesa openjdk-8-jdk wget
```
``curl git unzip xz-utils zip libglu1-mesa`` is required by Flutter SDK  
``openjdk-8-jdk`` is required by Android SDK  
``wget`` will be used for downloading some Android tools

```Dockerfile
RUN useradd -ms /bin/bash developer
USER developer
WORKDIR /home/developer
```
Add a new non-root user called **developer**, set it as the **current user**, and change the working directory to its **home** directory.

```Dockerfile
RUN mkdir -p Android/sdk
ENV ANDROID_SDK_ROOT /home/developer/Android/sdk
RUN mkdir -p .android && touch .android/repositories.cfg
```
Create some folders where the **Android SDK** will be installed. Also, set the environment variable ``ANDROID_SDK_ROOT`` to the correct directory path—this will be used by Flutter.

## Contributing
Pull requests are always welcome.  
👊
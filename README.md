# docker-android-sdk

This is an adjusted version of https://github.com/mindrunner/docker-android-sdk that is fitted for our specific purposes and needs.

The `latest`-tag points to the `alpine-standalone` Dockerfile.

This repository contains Dockerfiles to create Docker images containing the android SDK. There are two flavours for different use cases (lazydl, standalone) and two different linux bases (ubuntu, alpine). Feel free to chose which one suits you best.

* ubuntu-standalone
* ubuntu-lazydl
* alpine-standalone
* alpine-lazydl

**Ubuntu**
The officialy supported Linux distribution for Android SDK builds. Use this one if you are unsure, which is better.

**Alpine**
More lightweight Linux Distribution optimized for docker containers.

**Standalone**
This is the standard expected behaviour. The Android SDK is integrated in the docker image. Use this in your android build on CircleCI, Bitbucket Pipelines, or any other docker enabled CI.

**Lazydl**
Indeed, there is a lack of documentation and it might be not really intuitive to use the image in this way. The idea is to have two containers for the build process. One of which is the builing container executing the actual build. The other one is the sdk-data container, which downloads the whole SDK into a named docker volume which is shared between both containers.
I will provide an example docker-compose file to make this more clear. Might take a couple of days, though.

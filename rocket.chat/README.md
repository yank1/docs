# Supported tags and respective `Dockerfile` links

-	[`0.20.0`, `0.20`, `0`, `latest` (*Dockerfile*)](https://github.com/RocketChat/Docker.Official.Image/blob/b82f6b3e479f2166343018574bf8420998c17e77/Dockerfile)

[![](https://badge.imagelayers.io/rocket.chat:latest.svg)](https://imagelayers.io/?images=rocket.chat:0.20.0)

For more information about this image and its history, please see [the relevant manifest file (`library/rocket.chat`)](https://github.com/docker-library/official-images/blob/master/library/rocket.chat). This image is updated via pull requests to [the `docker-library/official-images` GitHub repo](https://github.com/docker-library/official-images).

For detailed information about the virtual/transfer sizes and individual layers of each of the above supported tags, please see [the `rocket.chat/tag-details.md` file](https://github.com/docker-library/docs/blob/master/rocket.chat/tag-details.md) in [the `docker-library/docs` GitHub repo](https://github.com/docker-library/docs).

# Rocket.Chat

Rocket.Chat is a Web Chat Server, developed in JavaScript, using the Meteor fullstack framework.

It is a great solution for communities and companies wanting to privately host their own chat service or for developers looking forward to build and evolve their own chat platforms.

![logo](https://rawgit.com/docker-library/docs/a6616e4fc5d554756247938b57677c763f32c0f4/rocket.chat/logo.svg)

# How to use this image

First, start an instance of mongo:

```console
$ docker run --name db -d mongo --smallfiles
```

Then start Rocket.Chat linked to this mongo instance:

```console
$ docker run --name rocketchat --link db -d rocket.chat
```

This will start a Rocket.Chat instance listening on the default Meteor port of 3000 on the container.

If you'd like to be able to access the instance directly at standard port on the host machine:

```console
$ docker run --name rocketchat -p 80:3000 --env ROOT_URL=http://localhost --link db -d rocket.chat
```

Then, access it via `http://localhost` in a browser. Replace `localhost` in `ROOT_URL` with your own domain name if you are hosting at your own domain.

If you're using a third party Mongo provider, or working with Kubernetes, you need to override the `MONGO_URL` environment variable:

```console
$ docker run --name rocketchat -p 80:3000 --env ROOT_URL=http://localhost --env MONGO_URL=mongodb://mymongourl/mydb -d rocket.chat
```

# License

View [license information](https://github.com/RocketChat/Rocket.Chat/blob/master/LICENSE) for the software contained in this image.

# Supported Docker versions

This image is officially supported on Docker version 1.10.2.

Support for older versions (down to 1.6) is provided on a best-effort basis.

Please see [the Docker installation documentation](https://docs.docker.com/installation/) for details on how to upgrade your Docker daemon.

# User Feedback

## Documentation

Documentation for this image is stored in the [`rocket.chat/` directory](https://github.com/docker-library/docs/tree/master/rocket.chat) of the [`docker-library/docs` GitHub repo](https://github.com/docker-library/docs). Be sure to familiarize yourself with the [repository's `README.md` file](https://github.com/docker-library/docs/blob/master/README.md) before attempting a pull request.

## Issues

If you have any problems with or questions about this image, please contact us through a [GitHub issue](https://github.com/RocketChat/Docker.Official.Image/issues).

You can also reach many of the official image maintainers via the `#docker-library` IRC channel on [Freenode](https://freenode.net).

## Contributing

You are invited to contribute new features, fixes, or updates, large or small; we are always thrilled to receive pull requests, and do our best to process them as fast as we can.

Before you start to code, we recommend discussing your plans through a [GitHub issue](https://github.com/RocketChat/Docker.Official.Image/issues), especially for more ambitious contributions. This gives other contributors a chance to point you in the right direction, give you feedback on your design, and help you find out if someone else is working on the same thing.

This is boilerplate for [docker-sync](https://github.com/EugenMayer/docker_sync).
Either as a starting point for your configuration or to try out what docker-sync offers in terms of performance and the toolchain in practical.

If you have issue, create a issue at [docker-sync](https://github.com/EugenMayer/docker_sync)

**Start with**

 1) Install docker-sync, if you did not yet

```
gem install docker-sync
```

There may be other dependencies that you will have to install but the `docker-sync-stack start` command should help with that. Known dependencies for Mac include: unison, macfsevent, fswatch. These are either installed automatically or you may have to `brew install` them.

 2) Now get the boilerplate
```
git clone https://github.com/EugenMayer/docker-sync-boilerplate
cd docker-sync-boilerplate
```

 3) Now start the sync, first choose the boilerplate either advanced, dynamic-configuration-dotnev, rsync, simplest, unison, unison-ftp-user, or unison-root-user. See [strategies](https://github.com/EugenMayer/docker-sync/wiki/8.-Strategies) to understand the important differences

---

## Examples

For example rsync
```
cd default
docker-sync-stack start
```
This will start the sync, and start your app-stack defined by in the docker-compose file. All in one step

---

If you wonder, how you would keep the docker-compose.yml portable, see splitted-compose (there is an example in the advanced example of this). The changes for docker-sync are incorporated into an overlay-docker-compose file
In this case you do:

```
# To run development and mount your watched volume.
cd advanced
docker-sync-stack start

# Production would run docker-compose without mounting a watched volume.
cd advanced/docker-compose
docker-compose up -d
```

More about this in [the wiki](https://github.com/EugenMayer/docker-sync/wiki/Keep-your-docker-compose.yml-portable)

---

For example __dynamic-configuration-dotnev__ you will need to __copy__ `.env.dist` to `.env`

```
cd dynamic-configuration-dotnev
cp .env.dist .env
## Change your settings to whatever you want and then run docker-sync.
docker-sync-stack start
```

And after that start things as described above


## Reference

If you want to know, what options you actually have, see the [configuration-reference](https://github.com/EugenMayer/docker-sync/wiki/2.-Configuration#docker-syncyml)

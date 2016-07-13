This is boilerplate for [docker-sync](https://github.com/EugenMayer/docker_sync).
Either as a starting point for your configuration or to try out what docker-sync offers in terms of performance and the toolchain in practical.

Start with

 1) Install docker-sync, if you did not yet

```
gem install docker-sync
```

 2) Now get the boilerplate
```
git clone https://github.com/EugenMayer/docker-sync-boilerplate
cd docker-sync-boilerplate
```

 3) Now start the sync, first choose the boilerplate either simplest, unison, rsync, splitted or even advanced

---

## Examples

For example rsync
```
cd rsync
docker-sync-stack start
```
This will start the sync, and start your app-stack defined by in the docker-compose file. All in one step

---

If you wonder, how you would keep the docker-compose.yml portable, see splitted-compose. The changes for docker-sync are incorporated into an overaly-docker-compose file
In this case you do:

```
cd splitted-compose
docker-sync start

<open a new shel>

cd splitted-compose
docker-compose -f docker-compose.yml -f docker-compose-dev.yml up
```

More about this in [the wiki](https://github.com/EugenMayer/docker-sync/wiki/Keep-you-docker-compose.yml-portable)

## Reference

If you want to know, what options you actually have, see the [configuration-reference](https://github.com/EugenMayer/docker-sync/wiki/2.-Configuration#docker-syncyml)
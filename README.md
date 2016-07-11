This is boilerplate for [docker-sync](https://github.com/EugenMayer/docker_sync).
Either as a starting point for your configuration or to try out what docker-sync offers in terms of performance and the toolchain in practical.

Start with

Install docker-sync, if yet did not
```
gem install docker-sync
```

Now the boilerplate
```
git clone https://github.com/EugenMayer/docker-sync-boilerplate
cd docker-sync-boilerplate
```

Now start the sync, first choose either unison or rsync ( you can actually mix both in a single docker-sync.yml)


```
cd rsync
docker-sync-stack start
```

This will start the sync, and start your app-stack defined by in the docker-compose file. All in one step

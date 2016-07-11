This is boilerplate for [docker-sync](https://github.com/EugenMayer/docker_sync)
Either start from here to implement fast volume-shares for you project or simply test
its performance

Start with

```
gem install docker-sync
git clone https://github.com/EugenMayer/docker-sync-boilerplate
cd docker-sync-boilerplate
```

Now start the sync, first choose either unison or rsync ( you can actually mix both in a single docker-sync.yml)


```
cd rsync
docker-sync-stack start
```

This will start the sync, and start your app-stack defined by in the docker-compose file. All in one step

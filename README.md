graphite-docker
===============

Graphite image for Docker


```shell
$ docker pull mackerel/graphite
$ docker run -d --name graphite -v /tmp/log:/var/log/graphite -v /tmp/whisper:/var/lib/graphite/storage/whisper -p 8000:8000 -p 2003:2003 -p 2004:2004 mackerel/graphite
```

## Tasting (on boot2docker 1.3.0 or later)

```shell
$ export BOOT2DOCKER_IP=`boot2docker ip 2>/dev/null`
$ echo "test.random.diceroll 4 `date +%s`" | nc $BOOT2DOCKER_IP 2003
$ curl http://$BOOT2DOCKER_IP:8000/render?target=test.random.diceroll&from=now-1h&format=json | jq .
```


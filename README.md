# Monitoring
 ## Loki Requirements
 For get Loki to work, you need to install a plugin, you can do it executing these command:
 
 `docker plugin install grafana/loki-docker-driver:latest --alias loki --grant-all-permissions`
 
 You need to install it on every node, after that, you need to create a "daemon.json" file on /etc/docker directory.
 
 ### content
 `{
    "debug" : false,
    "log-driver": "loki",
    "log-opts": {
        "loki-url": "http://127.0.0.1:3100/loki/api/v1/push"
    }
}
`

Is important to have the daemon.json on every node of swarm.

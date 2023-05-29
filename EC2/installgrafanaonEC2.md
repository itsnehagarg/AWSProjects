# Install Grafana Steps and commands on Ubuntu


```
 sudo apt-get update
```

## To install required packages and download the Grafana repository signing key, run the following commands:

```

sudo apt-get install -y apt-transport-https
sudo apt-get install -y software-properties-common wget
sudo wget -q -O /usr/share/keyrings/grafana.key https://apt.grafana.com/gpg.key

```

## To add a repository for stable releases, run the following command:

```

echo "deb [signed-by=/usr/share/keyrings/grafana.key] https://apt.grafana.com stable main" | sudo tee -a /etc/apt/sources.list.d/grafana.list

```

## To add a repository for beta releases, run the following command:

``` 
echo "deb [signed-by=/usr/share/keyrings/grafana.key] https://apt.grafana.com beta main" | sudo tee -a /etc/apt/sources.list.d/grafana.list

```


## Update the list of available packages

``` 
sudo apt-get update

```

## Install the latest OSS release:

``` 
sudo apt-get install grafana

```

## Install the latest Enterprise release:

``` 
sudo apt-get install grafana-enterprise

```

## Update the list of available packages

``` 
sudo apt-get update

```

## Install the latest OSS release:

``` 
sudo apt-get install grafana

```


``` 

sudo /bin/systemctl start grafana-server

sudo /bin/systemctl enable grafana-server

```

## Grafana details
Grafana runs at 3000 port. Enable Grafana port 3000 on Security group's Inbound rules (Lets say I will enable from My IP)

Grafana is up and running! :) Yay!! We did it!

We need to install Loki and Promtail


Grafana login: admin\admin
New Grafana pwd: test


### Loki Installation is through docker so first lets install docker on EC2:
``` 
sudo apt-get install docker.io 


sudo usermod -aG docker $USER

sudo reboot
``` 

### Create a directory for keeping the config files of Loki and Promtail:


### Download promtail and loki config using the below commands in the newly created directory:

``` 
wget https://raw.githubusercontent.com/grafana/loki/v2.8.0/cmd/loki/loki-local-config.yaml -O loki-config.yaml


wget https://raw.githubusercontent.com/grafana/loki/v2.8.0/clients/cmd/promtail/promtail-docker-config.yaml -O promtail-config.yaml


docker run -d --name loki -v $(pwd):/mnt/config -p 3100:3100 grafana/loki:2.8.0 --config.file=/mnt/config/loki-config.yaml
``` 

### Loki runs at 3100 port. Enable Loki port 3100 on Security group's Inbound rules (Lets say I will enable from My IP)

Hit the URL to access Loki:

http://<your EC2 IP>>:3100/ready

example:
http://54.189.189.22:3100/ready

#### To check the Metrics:

http://<your EC2 IP>>:3100/metrics


### Lets run Promtail now:

## Promtail will send logs to Loki:
``` 

docker run -d --name promtail -v $(pwd):/mnt/config -v /var/log:/var/log --link loki grafana/promtail:2.8.0 --config.file=/mnt/config/promtail-config.yaml

``` 








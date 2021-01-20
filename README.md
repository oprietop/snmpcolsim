# snmpcolsim
A k3d kubernetes deployment to test snmpcollector

## Setup
'''
curl -s https://raw.githubusercontent.com/rancher/k3d/main/install.sh | bash
mkdir -p storage
chmod 1777 storage
k3d cluster create snmpcollector -v $(pwd)/storage:/mnt -p "80:80@loadbalancer"
kubectl create -f k8s/.
'''

## Setdown
'''
k3d cluster delete snmpcollector
'''

## Notes
* Login to localhost:80 to get into snmpcollector
* add an influxdb server pointing to influxdb:8086
* add a snmp device pointing to snmpsimulator:1161
* You can check do a snmpwalk do 1.3 to get all the tree
